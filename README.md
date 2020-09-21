# RSPY

vulnerability scanner tool is using nmap and nse scripts to find vulnerabilities

This tool puts an additional value into vulnerability scanning with nmap. 
It uses NSE scripts which can add flexibility in terms of vulnerability detection and exploitation.
Below there are some of the features that NSE scripts provide  

- Network discovery
- More sophisticated version detection
- Vulnerability detection
- Backdoor detection
- Vulnerability exploitation

This tool uses the path ```/usr/share/nmap/scripts/``` where the nse scripts are located in kali linux 

The tool performs the following 

- check the communication to the target hosts by cheking icmp requests
- takes as input a protocol name such as http and executes all nse scripts related to that protocol
- if any vulnerability triggers it saves the output into a log file
- it may perform all of the above actions for a range of IP addresses

If the tool finds a vulnerabilty in a certain protocol (e.g http) it keeps the output into a log file which is created and saved in the following location ```/home/vulnerabilities_enumeration/http_vulnerabilities/http_vulnerabilities/http_vulnerabilities.txt``` 
In this example the folders have been created using the protocol prefix which in the current occasion is the http protocol. 

### Usage: 

```[Usage:] ./rspy.sh <ip_range> <protocol> <port> <Pn (optional)>```


```[Usage:] ./rspy.sh <ips_file> <protocol> <port> <Pn (optional)>```


```[Usage:] ./rspy.sh <ip> <protocol> <port> <Pn (optional)>```

### How to run:

1)
```./rspy.sh 192.168.162.90 http 80``` 

2)
```./rspy.sh 192.168.162.10-90 http 80```

3)
```./rspy.sh 192.168.162.90 ssh 22 Pn```

4)
```./rspy.sh IPs.txt smb 445 ```

### References :
- https://nmap.org/book/nse.html
- https://nmap.org/nsedoc/

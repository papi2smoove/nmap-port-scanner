
# nmap-port-scanner
Python script for scanning networks using Nmap, identifying open ports and services on target machines
Scans a target IP address for open ports.
# Clone the repository
git clone https://github.com/yourusername/nmap-network-scanner.git

# Navigate to the project directory
cd nmap-network-scanner

# Install the required Python packages
pip3 install python-nmap
# Run the script
python3 nmap_script.py
Host: 45.33.32.156 (scanme.nmap.org)
State: up
protocol: tcp
port: 22    state: open    name: ssh
port: 80    state: open    name: http

import nmap

nm = nmap.PortScanner()

target = "45.33.32.156"
options = "-sV -sC Scan_results"

nm.scan(target, arguments=options)

for host in nm.all_hosts():
    print("Host: %s (%s)" % (host, nm[host].hostname()))
    print("State: %s" % nm[host].state())
    for protocol in nm[host].all_protocols():
        print("protocol: %s" % protocol)
        Port_info = nm[host][protocol]
        for port, state in Port_info.items():
            2
            print("port: %s\tstate: %s" % (port, state))

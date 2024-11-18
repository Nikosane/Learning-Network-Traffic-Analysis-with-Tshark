# Learning-Network-Traffic-Analysis-with-Tshark


**What is Tshark?**

Tshark is a powerful command-line network protocol analyzer. It allows you to capture, view, and analyze network packets without a graphical interface, making it ideal for learning, scripting, or use on headless servers.

---

# Step 1: Verify Tshark Installation

Ensure tshark is installed on your Linux system. If not, install it using:
```
sudo apt update
sudo apt install wireshark
```
To confirm the installation:
```
tshark -v
```

---


# Step 2: List Available Interfaces

Before capturing packets, identify your network interfaces:
```
tshark -D
```

This will list all available interfaces, e.g.:

1. enp1s0
2. any
3. lo (Loopback)

---


# Step 3: Capture a Few Packets
Basic Capture

To capture only 5 packets:
```
sudo tshark -i enp1s0 -c 5
```
Verbose Output

To view detailed information about each packet:
```
sudo tshark -i enp1s0 -c 5 -V
```

Use the interface relevant to your network connection (e.g., enp1s0 for Ethernet or lo for localhost).


---


# Step 4: Save Packets for Later Analysis

To save the captured packets to a file for future analysis:
```
sudo tshark -i enp1s0 -c 5 -w sample.pcap
```

---

# Step 5: Apply Filters

Filters help capture only the traffic you're interested in. Below are some examples:
Capture DNS Traffic
```
sudo tshark -i enp1s0 -c 5 -f "port 53" -V
```
Capture HTTP Traffic
```
sudo tshark -i enp1s0 -c 5 -f "tcp port 80" -V
```
Capture Traffic for a Specific Host
```
sudo tshark -i enp1s0 -c 5 -f "host 192.168.1.1" -V
```
You can open sample.pcap in Wireshark or analyze it later using tshark:
```
tshark -r sample.pcap -V
```

---

# Tips for Running Tshark

- Use `tshark -D` to identify the correct interface.
- Run `tshark` with `sudo` if you encounter permissions issues.
- To avoid using `sudo`, add your user to the `wireshark` group:
```
sudo usermod -aG wireshark $USER
```
Log out and back in for the change to take effect.

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

Use the interface relevant to your network connection (e.g., enp1s0 for Ethernet or lo for localhost).

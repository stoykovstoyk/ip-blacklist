# IP Blacklist for Fail2Ban

This repository maintains a curated list of malicious IP addresses to be used with [Fail2Ban](https://www.fail2ban.org/) or other intrusion prevention tools. It helps automate the process of banning known bad actors from accessing your services.

## 📦 Features

- Regularly updated list of banned IP addresses
- Designed for easy integration with Fail2Ban, iptables, or firewalls
- Simple format for scripting and automation

## 📂 Repository Structure

ip-blacklist/

├── blacklist.txt # List of banned IPs (one per line)

├── README.md # Project documentation


## ⚙️ Usage

### With Fail2Ban

You can include this blacklist as part of your Fail2Ban action configuration:

1. **Append to iptables**:
   ```bash
   while read ip; do
     iptables -A INPUT -s "$ip" -j DROP
   done < blacklist.txt

    Automate with a cron job:

    0 * * * * /path/to/update.sh && systemctl restart fail2ban

With Other Tools

The blacklist.txt file can be used by:

    Nginx/Apache blocklists

    Cloud firewall rules

    Host-based intrusion detection systems

✍️ Contributing

If you have a list of malicious IPs or want to contribute improvements, feel free to open a pull request.

Please ensure the IPs are:

    Confirmed malicious (e.g. botnets, brute force, spam)

    Not dynamic or innocent sources (e.g. NAT-ed ISPs)

📜 License

MIT License. Use at your own risk — always audit IP lists before applying to production.
🙏 Acknowledgements

Thanks to the open-source security community and tools like Fail2Ban for making the internet safer.


---

Let me know if you want a version that includes automation with APIs, third-party blacklists, or if it's meant for a different use case.



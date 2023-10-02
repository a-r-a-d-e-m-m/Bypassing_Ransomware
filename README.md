# Bypassing_Ransomware

A few weeks later, I received a notification that one of the servers affected by the Log4j vulnerability had been compromised with ransomware. The server was used to store sensitive customer data, and I knew I had to act quickly to prevent the data from being misused.

I started by running a scan of the server to see what files had been accessed. I found that the attackers had accessed a number of files, including some that contained customer names, addresses, and social security numbers.

I then used a brute force script to crack the password that the attackers had used to encrypt the files. Once I had the password, I was able to unlock the files that the attackers had accessed.

Here's the script:
```
from zipfile import ZipFile

def attempt_extract(zf_handle, password):
    try:
        zf_handle.extractall(pwd=password)
        return True
    except:
        return False

def main():
    print("[+] Beginning bruteforce ")
    with ZipFile('enc.zip') as zf:
        with open('rockyou.txt', 'rb') as f:
            for p in f:
                password = p.strip()
                if attempt_extract(zf, password):
                    print("[+] Correct password: %s" % password)
                    exit(0)
                else:
                    print("[-] Incorrect password: %s" % password)

    print("[+] Password not found in list")

if __name__ == "__main__":
    main()
```

I then restored the server to its original state and notified the team leads of the incident. The team leads were grateful for my quick action, and they were able to notify the affected customers of the breach.

* * *

I was proud of my work in resolving the server compromise, and I knew that I had made a difference in protecting customer data. I was also excited to continue my work with the Shields Up: Cybersecurity program, and I knew that I was learning valuable skills that would help me in my future career.

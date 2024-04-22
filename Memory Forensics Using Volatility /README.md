## Below Commands will use the Volatility tool to analyze malware sample in memory dump. 

```
python3 vol.py -f sample.vmem windows.pstree
```
### 1. Install Volatility Tool by extracting tar file 
```
sudo tar -xvzf volatility3new.tar.gz
```

![image](https://github.com/KVNuhman/Cyber-Forensics/assets/46161259/fbeef1e2-801f-4a6c-83c3-a88af1df7a02)

### 2. Perform Malware Analysis using Volatility tool

```
python3 vol.py -f sample.vmem windows.pstree
```

![image](https://github.com/KVNuhman/Cyber-Forensics/assets/46161259/e21aff92-3fb6-40e3-a3b2-2891cbd9b68c)

![image](https://github.com/KVNuhman/Cyber-Forensics/assets/46161259/c0d15c17-6d55-474b-a60a-2b3a4f4dc83e)

# Connecting other device to localhost in the same network
## Option 1: Using network profile
* change network profile to private
## Option 2: Using PowerShell in administration mode
1. Open up PowerShell as administrator.
2. Run command ```Get-NetConnectionProfile``` then a list of properties will appear.
```
Name            : Network
InterfaceAlias  : Ethernet
InterfaceIndex  : 14
NetworkCategory : Public
...
```
3. Change **Networkcategory** to public. Please specify **InterfaceIndex**:
```Set-NetConnectionProfile -InterfaceIndex 14 -NetworkCategory Private```
4. Find out your current local IP address of your computer. It is the one the wifi router assign for you computer by running ```ipconfig```
5. Your computer IP address may reside in **Ethernet adapter Ethernet** or **Wireless Lan ethernet**. The one we are looking for is IPv4 _**192.168.x.x**_
6. Go to your phone browser and enter either ***192.168.x.x:3000** (3000 is the port you run your application, it might differ depend on you). Also remember **http://192.168.x.x:3001** is the standard link if you want your phone to make request to local server endpoint, that is the standard format of the endpoint instead of just **192.168.x.x:3001**


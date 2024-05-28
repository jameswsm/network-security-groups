![image](https://github.com/jameswsm/network-security-groups/assets/170709350/6b8b1220-740d-4ef4-8c21-f221f34b8332)
</p>

<h1>Azure Network Security Groups(NSGs)</h1>
Tutorial for Network Security Groups<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Users and Computers

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Microsoft Azure Active Subscription (Creation of Reasearch Group, VMs, Virtual Networks, Subnets)
- Active Directory running in Azure on a virtual machine (DC1)
- Client machine running in Azure on a VM (Client1) and joined to the domain
- Folders/Groups created in "Sharing Resources Over The Network With Permissions"

<h2>Steps: 1 - 7</h2>

![image](https://github.com/jameswsm/network-security-groups/assets/170709350/108c57a1-b475-4284-9edf-5dd647588a47)
<p>
Step 1: Log into DC1 -> Active Directory Users and Computers -> mydomain.com -> New -> Organizational Unit -> Name: _SECURITY_GROUPS
</p>
<br />

![image](https://github.com/jameswsm/network-security-groups/assets/170709350/a28b9fee-3beb-4648-93fe-65fa55f46f99)
<p>
Step 2: _SECURITY_GROUPS -> New -> Group -> Group Name: ACCOUNTANTS, Group Type: Security -> Ok
</p>
<br />

![image](https://github.com/jameswsm/network-security-groups/assets/170709350/7af93eb2-2906-4ea0-8eb3-9525e67446aa)
<p>
Step 3: ThisPC -> Windows(C:) -> accounting -> Properties -> Sharing -> Share -> add ACCOUNTANTS -> Permission Level: Read/Write -> Share
</p>
<br />

![image](https://github.com/jameswsm/network-security-groups/assets/170709350/f0902303-fdb6-4e3d-bbcd-fcd7e617e33e)
<p>
Step 4: Log into Client1 -> Attempt to access accounting folder from generic user(ex:bes.jom) who is NOT in the ACCOUNTING group
</p>
<br />

![image](https://github.com/jameswsm/network-security-groups/assets/170709350/b49b38a7-1d8d-4947-97aa-2fa70c2f4544)
<p>
Step 5: Log into DC1 -> Active Directory Users and Computers -> _SECURITY_GROUPS -> ACCOUNTANTS -> Members -> Add... -> Enter username(ex:bes.jom) -> Check Names -> Ok -> Apply -> Ok
</p>
<br />

![image](https://github.com/jameswsm/network-security-groups/assets/170709350/14593e4b-78f5-45f9-8deb-eb95785da182)
<p>
Step 6: Log out of Client1(to refresh new permissions) -> Log back in as user(ex: bes.jom)
</p>
<br />

![image](https://github.com/jameswsm/network-security-groups/assets/170709350/78dfd4f4-d5c9-4375-891b-41655189de34)
<p>
Step 7: Navigate to \\dc1 -> attempt to open accounting folder -> success!
</p>
<br />

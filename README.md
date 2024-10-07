<h1>Azure Private Link & Firewall for Resources: NIST SC-7</h1>

- <b>This tutorial outlines the configuration of Private Endpoints for our key vault and storage account</b>

<h2>Environments and Technologies Used</h2>

- <b>Microsoft Azure</b> 
- <b>Private Endpoint</b>
- <b>Key Vault</b>
- <b>Storage Account</b>
- <b>NIST SC-7</b>

<h2>Operating Systems</h2>

- <b>Windows 10</b>

<h2>Configuration Steps</h2>

![image](https://github.com/user-attachments/assets/178f094c-9f94-402f-a76f-ed7206f611ba)
- <b>Navigate to key vaults and click networking</b>
- <b>Select Disable public access and allow trusted Microsoft services to bypass this firewall</b>

![image](https://github.com/user-attachments/assets/fc3a8a0b-b17f-4275-9bd3-df9c117c2834)
- <b>Click Private endpoint connections and create</b>
- <b>Subscription: Azure Subscription 1</b>
- <b>Resource Group: RG-Cyber-Lab</b>
- <b>Name: PE-AKV</b>
- <b>Region: EAST US 2</b>
- <b>Click next: resource</b>

![image](https://github.com/user-attachments/assets/ffe40c46-2f7e-42fa-9f95-2f4649aa44ff)
- <b>Connection method: Connect to an Azure resource in my directory</b>
- <b>Resource Group: RG-Cyber-Lab</b>
- <b>Resource: akv-cyber-lab-12345</b>
- <b>Target sub-resource: vault</b>
- <b>Click review + create</b>

![image](https://github.com/user-attachments/assets/95dd0bc5-572c-49c8-8275-f4bb8bc9e7ad)
- <b>Private Endpoint Creation</b>

![image](https://github.com/user-attachments/assets/cec79316-0db7-49c0-91f3-4c971affd379)
- <b>Navigate to storage accounts and click networking</b>
- <b>Public network access: disabled</b>
- <b>Click private endpoint connections</b>

![image](https://github.com/user-attachments/assets/bc91468d-6554-4cd8-829e-437e14006855)
- <b>Click Private endpoint connections and create</b>
- <b>Subscription: Azure Subscription 1</b>
- <b>Resource Group: RG-Cyber-Lab</b>
- <b>Name: PE-Storage</b>
- <b>Region: EAST US 2</b>
- <b>Click next: resource</b>

![image](https://github.com/user-attachments/assets/e81e92d6-2624-40aa-91e7-24c7fbf49d1d)
- <b>Target sub-resource: blob</b>
- <b>Click review + create</b>

![image](https://github.com/user-attachments/assets/aa53c3b0-97fd-4d88-b32c-bacd84f55ca1)
- <b>Private Endpoint Creation</b>

![image](https://github.com/user-attachments/assets/21d0e029-d5ba-4ae0-8dd4-c2665c4533e5)
- <b>Navigate to Network Watcher and click Topoloy</b>
- <b>Click EAST US 2</b>

![image](https://github.com/user-attachments/assets/e1ce102b-1d1d-4814-aae4-bae9f17bf465)
- <b>Lab Virtual Network</b>

![image](https://github.com/user-attachments/assets/78719b99-330e-49a6-8af4-4c08a510d389)
- <b>Private Endpoint for Azure Key Vault</b>

![image](https://github.com/user-attachments/assets/2397fdd8-0d69-44e1-ac43-919a8150a5ce)
- <b>Private Endpoint for Storage accounts</b>

![image](https://github.com/user-attachments/assets/4e13fb63-1cb5-4cd4-9e1f-e7f90fe3f90d)
- <b>Navigate to Key Vault and copy vault URL</b>
- <b>Login to Windows-vm and open PowerShell</b>

![image](https://github.com/user-attachments/assets/e106d654-c34f-4291-9d39-065fb47b6510)
- <b>nslookup for key vault</b>


![image](https://github.com/user-attachments/assets/39d3a803-21d6-4659-989b-f683978995db)
- <b>Navigate to Storage account and click endpoint</b>
- <b>Copy blob service URL</b> 
- <b>nslookup for storage account</b>

![image](https://github.com/user-attachments/assets/61938ada-d294-4740-89e8-5a5e787a867b)
- <b>nslookup for key vault from host computer</b>

![image](https://github.com/user-attachments/assets/f0bcedce-3737-48a5-b24f-4152e57ff61c)
- <b>nslookup for storage account from host computer</b>

![image](https://github.com/user-attachments/assets/9fc8cf62-57df-4770-8c70-4f873451ab08)
- <b>Navigate to Network Security Group and click create</b>
- <b>Subscription: Azure Subscription 1</b>
- <b>Resource Group: RG-Cyber-Lab</b>
- <b>Name: nsg-subnet</b>
- <b>Region: EAST US 2</b>

![image](https://github.com/user-attachments/assets/364a7b84-1283-412b-92c5-10638301f4c1)
- <b>Navigate to Virtual Network and click Lab-VNet</b>
- <b>Click subnets and select default</b>
- <b>Network Security Group: nsg-subnet</b>

![image](https://github.com/user-attachments/assets/a1215359-247e-414e-9d51-38abe461f411)
- <b>Navigate to Network Watcher</b>
- <b>Cick EAST US 2</b>

![image](https://github.com/user-attachments/assets/0808d751-832d-498b-8497-7d4024e5ec25)
- <b>Navigate to Microsoft Defender for Cloud and click regulatory compliance</b>
- <b>Select SC-7: Boundary Protection and click SC-7: Additional assessments for SC-7 - Boundary Protection</b>

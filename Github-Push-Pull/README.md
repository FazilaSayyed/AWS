<h1>GITHUB</h1>
<h2>PUSHED FROM LOCAL REPOSITORY TO REMOTE REPOSITORY BY SSH</h2>
<h3>Step 1: Create Instance and select Ubuntu (ubuntu has by default git installed)</h3>

![image](https://github.com/user-attachments/assets/7edece00-5e62-49fe-a08e-a0357ee02b39)

<h3>Step 2: Connect Instance</h3>

```
mkdir new
touch index.txt
echo “My name is Aaman I am DevOps engineer” >                 
index.txt
ssh-keygen (generate new key pair)
cat /new/.ssh/<pubkey> (copy public key and paste it in github setting )
```

![image](https://github.com/user-attachments/assets/de1ff5ff-7428-42c9-99fc-40d2494839b5)

```
git remote add origin git@github.com:Aamantamboli/new.git
git branch -M main
git push -u origin main
```

![image](https://github.com/user-attachments/assets/835560b8-bab4-4d5f-8996-a709e858914d)

**Successfully pushed local repository to remote repository**

<h1>PULL FROM REMOTE REPOSITORY TO LOCAL REPOSITORY BY SSH</h1>
<h3>Step 1: Create Instance and select Ubuntu (ubuntu has by default git installed)</h3>

![image](https://github.com/user-attachments/assets/e24253d9-e80a-4c8d-b11f-830c2eee76a3)

<h3>Step 2: Connect Instance</h3>

```
git clone git@github.com:Aamantamboli/new.git
cat new/index.html
```

![image](https://github.com/user-attachments/assets/3eb03dd8-3fe4-4034-b2f6-876e547337c7)

<h3>Step 3: Edit file </h3>

![image](https://github.com/user-attachments/assets/72194bf1-ecbf-4eaa-8109-3d716777ccb3)

<h3>Step 4: Now pull it</h3>

```
cd new/
git pull 
```

![image](https://github.com/user-attachments/assets/82cbe144-6e4e-48ba-8514-bf37cea4ec8f)

**Successfully pulled from remote repository to local repository**

<h2>PUSHED FROM LOCAL REPOSITORY TO REMOTE REPOSITORY BY PAT (PERSONAL ACCESS TOKEN)</h2>
<h3>Step 1: Go to Github setting select developer setting and then click on personal access token and generate new token</h3>

![image](https://github.com/user-attachments/assets/958c23ad-84be-4890-a52a-7973865cb226)

<h3>Step 2: Give scopes to that token </h3>

![image](https://github.com/user-attachments/assets/ce927b46-d1e5-4bd9-90d1-0788c12b9b11)

<h3>Step 3: Save this token because it is visible at once only </h3>

![image](https://github.com/user-attachments/assets/8b6c5ffe-c85c-4eb3-be40-18e2b4c91a3e)

<h3>Step 4: Create new Instance and connect it </h3>

![image](https://github.com/user-attachments/assets/afe8adf3-0d16-4185-8bd8-e39e9cb175cd)

```
git clone https://<token>@github.com/Aamantamboli/new.git
ls
cd new/
echo “MY NAME” > index1.txt
git add .
git commit -m”17-08-2024” 
git push 
```

<h3>Step 5: Successfully pushed file to repository</h3>

![image](https://github.com/user-attachments/assets/75490363-0ca5-41c6-82ab-63df3c798b44)

<h2>PULLED FROM REMOTE REPOSITORY TO LOCAL REPOSITORY BY PAT (PERSONAL ACCESS TOKEN)</h2>
<h3>Step 1: Go to Github setting select developer setting and then click on personal access token and generate new token</h3>

![image](https://github.com/user-attachments/assets/d429631d-0aef-4d9d-9a0d-4dc19c3ba414)

<h3>Step 2: Give scopes to that token </h3>

![image](https://github.com/user-attachments/assets/6c749704-11d5-413f-8cca-cdc0508164df)

<h3>Step 3: Save this token because it is visible at once only </h3>

![image](https://github.com/user-attachments/assets/a842a45e-c558-484b-b8ee-c983d4750685)

<h3>Step 4: Create new Instance and connect it </h3>

![image](https://github.com/user-attachments/assets/d9015f7b-35ce-45c0-a32f-29bcffada6a6)

```
git clone https://<token>@github.com/Aamantamboli/new.git
```

<h3>Step 5: Upload or create new file in the repository </h3>

![image](https://github.com/user-attachments/assets/bfdda766-4852-4c7d-ad4c-e8ca92695042)

```
cd new/
git pull
```
<h3>Step 6: Your file will be successfully pulled</h3>

![image](https://github.com/user-attachments/assets/cb75fe7d-3a44-4052-a2f1-ade463eb8cbd)

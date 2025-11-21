# gensyn-codeassist-with-vps
**This guide is only for people who want to run gensyn CodeAssist with VPS**

I am going to keep this as short and easy as possible 
I tried using my PC to run the gensyn codeassist but i ended up having multiple issues and had to start all over again and again but then i simply got a vps from servarica and since i set it up i havent got any issues and I'm now ranked 15th in codeasisst leaderboard 

## 1) Get a $14 a month VPS

goto servarica
https://clients.servarica.com/aff.php?aff=1166

from the menu click on KVM VPS PLANS
select the KVM Slim Slice 8 32gb RAM
cost $14

<img width="431" height="228" alt="Screenshot 2025-11-21 at 14 17 26" src="https://github.com/user-attachments/assets/fd99143b-b9e3-4f20-9d75-e2911bc0852f" />


you can pay with your wallet (USDC base chain)
or send crypto to the address given to you 

you can use your nickname as the hostname 
and select ubuntu24 from the "VM Template"

after payment your VPS should be ready in 30 mins to 2hr

## 2) Log into your vps on Termius software

you vps email should have your vps IP (xx.xxx.xx.xxx) and a password  
you can also see all this from your servarica client portal
login to termius software using root as your username

## 3) Run these codes 

once you are in, your terminal point should look like this 

<img width="511" height="120" alt="root" src="https://github.com/user-attachments/assets/351a84c5-e625-4bd1-96f6-7d0153f262a9" />  


**copy and run the below codes to setup your codeassist environments**

1)

```
sudo apt update && sudo apt install -y python3 python3-venv python3-pip curl wget screen git lsof gnupg && curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash - && sudo apt update && sudo apt install -y nodejs && sudo mkdir -p /etc/apt/keyrings && curl -fsSL https://dl.yarnpkg.com/debian/pubkey.gpg | sudo gpg --dearmor -o /etc/apt/keyrings/yarn.gpg && echo "deb [signed-by=/etc/apt/keyrings/yarn.gpg] https://dl.yarnpkg.com/debian stable main" | sudo tee /etc/apt/sources.list.d/yarn.list > /dev/null && sudo apt update && sudo apt install -y yarn && node -v && npm -v && yarn -v
```

2)

```
curl -fsSL https://get.docker.com | sudo sh
```

3)

```
git clone https://github.com/gensyn-ai/codeassist
```

4)

```
curl -LsSf https://astral.sh/uv/install.sh | sh
```

5)

```
npm install -g localtunnel
```

## 4) Run Code Assist

after all the installations above 

run
```
cd codeassist
```

this will take you into the codeassist directory now run

```
uv run run.py --port 3001
```

this will take a few minutes as it will install alot of files being that its your first time 

it gets to a point where it asks for your Hugging face token
copy the token you have created from hugging face website   
( https://huggingface.co/settings/tokens )

<img width="990" height="258" alt="hf" src="https://github.com/user-attachments/assets/101cd115-1e6e-48fa-9c5e-f3de37c5417e" />  

once codeassist is done running you will see the below image 

<img width="1127" height="223" alt="O-eURNe3" src="https://github.com/user-attachments/assets/1d683a61-0baf-4f2a-abfe-e87a3983ac3b" />

connecting to the localhost is how we can login to our gensyn account so that our participation can be recorded, this was why we installed a tunnel dependency earlier  

so at the point the next thing to do it to right click on your IP tab (on termius) and click on duplicate

<img width="536" height="143" alt="C1htAJPB" src="https://github.com/user-attachments/assets/0a6b324d-5e49-4c10-b950-2ad731b72037" />  

this will open another tab for you  
now you run this code below  


```
lt --port 3001
```

this should bring up a link for you 

<img width="640" height="116" alt="DhbVaBkP" src="https://github.com/user-attachments/assets/76fff56a-af6f-4c99-a725-178e28421ca0" />

hold "ctrl" key and click on the link

this will then open a page on your browser  

the password it's asking for is your vps IP address  


<img width="1068" height="346" alt="XxAQNIW3" src="https://github.com/user-attachments/assets/32eb6138-0675-4eab-b25e-ac3a8456f78a" />
  
hit "click to submit" button 

this will then take you to codeassist website where you login with your email and then try to solve the code problems presented to you.  

after a successful section, go back to your first tab in termius software where your codeassist is running and hit "crtl + C " to save your training 
  

<img width="1127" height="223" alt="O-eURNe3" src="https://github.com/user-attachments/assets/a883aa3f-15d6-4176-bb56-686dd28362ac" />

  
once its done you should receive your participation on your gensyn testnet dashboard.  
.  

if this was helpful to you  
pls share the tweet > https://x.com/yakymoney/status/1991874133039415439



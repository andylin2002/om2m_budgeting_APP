# om2m_budgeting_APP

## Introduction
"This user-friendly budgeting application aims to cultivate consistent financial tracking habits, minimizing the time commitment often associated with complex accounting apps and ensuring that managing finances does not impede one's enjoyment of life."

## 🚀 Usage
### 1. Open your Om2m MN-CSE and IN-CSE
MN-CSE
```
cd org.eclipse.om2m/org.eclipse.om2m.site.mn-cse/target/products/mn-cse/linux/gtk/x86_64
```

```
sh start.sh
```
IN-CSE
```
cd org.eclipse.om2m/org.eclipse.om2m.site.in-cse/target/products/in-cse/linux/gtk/x86_64
```

```
sh start.sh
```
It would like the screen below:
![MN-CSE and IN-CSE set up](./readme_images/mn&in.png)

### 2. Node-Red

You need to download **node red** before type the command
```
node-red
```
![](/readme_images/nodered.png)
After that, you can connect the link: **http://localhost:1880**

Use flow.json to build the budgeting app's environment setup tool on node-red.

Click three bottons to build Alice's AE and container on MN-CSE:
![](/readme_images/nodered_Alice_personal.png)

Click three bottons to build Bob's AE and container on MN-CSE:
![](/readme_images/nodered_Bob_personal.png)

Build up successfully:
![](/readme_images/MNCSE_personal.png)

### 3. Postman
Next, we need to use Postman to establish the subscription relationship between the MN and the IN. This will allow data received by the MN to be smoothly transmitted to the IN. Please use `/om2m_money.postman_collection.json`

Send all the **post** (four in total) in **om2m_money** folder:
![](./readme_images/postman.png)

After that:

<div style="display: flex; justify-content: center;">
  <img src="./readme_images/MNsub.png" alt="MNsub" style="width: 48%; margin-right: 2%;">
  <img src="./readme_images/INsub.png" alt="INsub" style="width: 48%;">
</div>

### 4. APP
Before uploading, users will need to enter an amount and a description. Once these are entered, pressing the Upload button will send the record to the Middle Node (MN). Alice's and Bob's records will be stored in separate containers on the MN.
![](./readme_images/personal_post.png)

To review past spending, simply enter a date (e.g., 20250522) to retrieve that day's transaction records.
![](./readme_images/personal_get.png)

Next is Group Mode. The goal is that when users switch to Group Mode, every amount entered will be treated as a "group expense."\
When Alice and Bob, each in Group Mode, upload these expenses to their respective Middle Nodes (MNs), the system will use a subscription mechanism to transfer this data to the Infrastructure Node (IN). However, each of their MNs will only be able to see the expenses they personally uploaded.
![](./readme_images/group_post.png)

Later, if either party wants to see the total group spending and balance for a specific day, they just need to enter that date in the app. This will show them how much they still need to pay or receive.
![](./readme_images/group_get.png)

## 👤 Author
Developed by Tzu-Chuan, Lin

## 📄 License

This project is provided for academic and educational use only. You may extend or modify it freely.
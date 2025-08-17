Got it ✅. I’ll draft a **professional README** for your project based on the details in the uploaded PDF. It will summarize the purpose, features, architecture, installation steps, usage, and protocols in a structured way so that anyone can understand and run the project.  

***

# Ethernet Communication Between Two PCs – Timer Synchronization  

## 📌 Project Overview  
This project demonstrates **real-time Ethernet communication** between two computers (PC1 and PC2) using **Python socket programming and Tkinter GUI**.  

The system simulates a **synchronized timer application**, where:  
- **PC1** hosts the main timer with controls (Start, Stop, Reset)  
- **PC2** mirrors the timer updates and can optionally send control commands back to PC1  
- Communication occurs via **TCP/IP sockets** over Ethernet (local network or localhost)  

The model highlights fundamentals of **client-server networking, real-time GUI synchronization, and bidirectional data exchange**.  

***

## ✨ Key Features  
- 🔑 **Login GUI** – Secure login authentication (PC1 Login Window).  
- ⏱️ **Timer Application** – Start, Stop, and Reset functions with hour, minute, second counters.  
- 🌐 **Ethernet Communication** – Exchange timer values and control signals over IP + Port.  
- 📡 **Two-way Synchronization** – PC1 → PC2 (Timer Updates) and PC2 → PC1 (Control Commands / ACK).  
- 🖼️ **File Transfer Support** – Optional **image transfer feature** from PC1 to PC2.  
- 📋 **Data Logging** – Received timer values and statuses are logged with timestamps on PC2.  

***

## ⚙️ System Requirements  

### Software  
- **Python 3.8+**  
- Libraries:  
  - `tkinter` (GUI)  
  - `socket` (Networking)  
  - `threading` (Concurrency)  
  - `json` (Data serialization)  
  - `PIL` / `Pillow` (Image Handling, PC2)  

### Hardware  
- Two PCs on the **same LAN** (or single PC with localhost testing)  
- Ethernet/Wi-Fi connectivity  

***

## 🖥️ Application Architecture  

- **PC1 (Controller)**  
  - Login window → Timer App  
  - Generates timer values (HH:MM:SS)  
  - Sends JSON packets to PC2 continuously  
  - Accepts ACK or control commands from PC2  

- **PC2 (Receiver)**  
  - Receives packets from PC1  
  - Updates mirrored timer display  
  - Logs received data with timestamps  
  - Can send acknowledgments/control events  

- **Network Protocol**  
  - TCP sockets over defined IP/Port  
  - JSON-based structured communication  

***

## 📡 Communication Protocol  

**PC1 → PC2**  
- Sender ID (`PC1`)  
- Receiver ID (`PC2`)  
- Hours, Minutes, Seconds  
- Timer Status (`running`/`stopped`)  
- Timestamp  

**PC2 → PC1**  
- Sender ID (`PC2`)  
- Receiver ID (`PC1`)  
- ACK Status (`received`) OR Control signals (Start/Stop/Reset)  
- Timestamp  

***

## 🚀 How to Run  

### 1. Clone / Extract Project  
Place all files in one directory:  
- `main.py`  
- `login_window.py`  
- `pc1_timer.py`  
- `pc2_receiver.py`  
- `network_utils.py`  

### 2. Install Dependencies  
```bash
pip install pillow
```

(`tkinter`, `json`, `threading`, and `socket` come with Python standard library.)  

### 3. Run Main Launcher  
```bash
python main.py
```

### 4. Choose Role  
- Select **PC1 (Timer + Login)** to run as the main controller  
- Select **PC2 (Receiver)** to run as the receiver/mirror  

### 5. Login (PC1)  
- Default credentials:  
  - **Username:** `admin`  
  - **Password:** `password`  

### 6. Start Communicating  
- Use **Start/Stop/Reset** on PC1 → PC2 mirrors it in real time  
- View status and logs on PC2  

***

## 📦 Project Structure  

```
├── main.py             # Launcher to choose PC1 or PC2
├── login_window.py     # Login screen for PC1
├── pc1_timer.py        # Timer GUI + Networking for PC1
├── pc2_receiver.py     # Receiver GUI for PC2
├── network_utils.py    # Socket and communication utilities
├── received/           # Folder for received images
```

***

## 🔍 Example Workflow  

### PC1 (Controller):  
1. User logs in → Enters Timer Window  
2. Starts timer → Sends updates (`HH:MM:SS`, status) to PC2  
3. Optionally, sends image file  

### PC2 (Receiver):  
1. Listens for messages from PC1  
2. Updates mirrored GUI timer with received values  
3. Logs messages with timestamps  
4. Sends back “ACK” or control commands  

***

## ✅ Conclusion  

This project is a **practical demo of distributed applications** where multiple PCs share synchronized states via Ethernet. It is useful for learning:  
- Socket Programming (TCP/UDP communication)  
- Real-time Systems with GUI  
- Client-Server Model in Networking  
- Multithreading for smooth GUI + networking  

***

## 📚 References  
- Python Official Docs – `socket` & `tkinter`  
- GeeksforGeeks / RealPython – Socket Programming Tutorials  
- Pillow (PIL fork) for image processing  

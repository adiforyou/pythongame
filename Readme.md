# 🎮 **Tic-Tac-Toe Game using Python (Tkinter)**  

## 📝 **About the Project**  
This is a **simple Tic-Tac-Toe game** built using **Python** and **Tkinter**. It features a graphical user interface where two players can play alternately, and the game automatically detects the winner.  

## 🚀 **Features**  
✅ **Interactive GUI** built with Tkinter  
✅ **Two-player support** (X and O take turns)  
✅ **Winner detection** with message box  
✅ **Draw detection**  
✅ **Lightweight and easy to run**  



## 📌 **Installation & Setup**  
### 1️⃣ **Clone the Repository**  
```bash
git clone https://github.com/adiforyou/pythongame
cd ti.py
```

### 2️⃣ **Run the Game**  
```bash
python ti.py
```

## 🛠 **Code Explanation**  
### **1. Import Required Libraries**  
```python
import tkinter as tk
from tkinter import messagebox
```
- `tkinter` for GUI  
- `messagebox` for pop-up alerts  

### **2. Create the Main Window**  
```python
root = tk.Tk()
root.title("Tic-Tac-Toe")
```
- Initializes the GUI window  

### **3. Create the 3x3 Grid of Buttons**  
```python
buttons = [tk.Button(root, text="", font=("normal",25), width=6, height=2, command=lambda i=i: button_click(i)) for i in range(9)]
```
- Creates a list of **9 buttons** for the game grid  

### **4. Place Buttons in the Grid**  
```python
for i, button in enumerate(buttons):
    button.grid(row=i//3, column=i%3)
```
- Arranges buttons in a **3x3 layout**  

### **5. Handle Button Clicks**  
```python
def button_click(index):
    if buttons[index]["text"] == "" and not winner:
        buttons[index]["text"] = current_player
        check_winner()
        toggle_player()
```
- Updates the button text on click  
- Calls `check_winner()` after every move  

### **6. Check for a Winner**  
```python
def check_winner():
    for combo in [[0,1,2], [3,4,5], [6,7,8], [0,3,6], [1,4,7], [2,5,8], [0,4,8], [2,4,6]]:
        if buttons[combo[0]]["text"] == buttons[combo[1]]["text"] == buttons[combo[2]]["text"] != "":
            messagebox.showinfo("Tic-Tac-Toe", f"Player {buttons[combo[0]]['text']} wins!")
            root.quit()
```
- Checks **all possible winning combinations**  
- Displays a winner message if found  

### **7. Switch Player Turns**  
```python
def toggle_player():
    global current_player
    current_player = "X" if current_player == "O" else "O"
    label.config(text=f"Player {current_player}'s turn")
```
- Changes the turn between **"X" and "O"**  

### **8. Display Current Player Turn**  
```python
label = tk.Label(root, text=f"Player {current_player}'s turn", font=("normal",16))
label.grid(row=3, column=0, columnspan=3)
```
- Displays which player's turn it is  

## 🛡 **License**  
This project is **open-source** and available under the [MIT License](LICENSE).  

## 🤝 **Contributing**  
Contributions are welcome! If you'd like to improve this project:  
1. Fork the repository  
2. Create a new branch (`git checkout -b feature-branch`)  
3. Commit changes (`git commit -m "Add new feature"`)  
4. Push to the branch (`git push origin feature-branch`)  
5. Open a Pull Request  

## 🌟 **Support & Feedback**  
If you like this project, consider ⭐ starring the repository! For feedback, open an issue or reach out.  


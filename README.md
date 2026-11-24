# ⏰ Digital Clock Using Java Swing

> *"Every big developer journey starts with a single line of code."*  
> Welcome to my very first Java project! Building this real-time digital clock was my first hands-on step into GUI development and event-driven programming.

---

## 🎯 Objective
To create a lightweight, GUI-based digital clock using **Java Swing** that fetches the current system time and updates every second in real-time.

---

## 🛠️ Technology Used
- **Language:** Java
- **Library:** Java Swing (`JFrame`, `JLabel`, `Timer`)
- **IDE (Optional):** IntelliJ IDEA, Eclipse, NetBeans, or VS Code 

---

## 🧱 Components Used

| Component | Purpose |
| :--- | :--- |
| `JFrame` | Main window container for the GUI |
| `JLabel` | Displays the time in text format |
| `Timer` | Automatically updates the time every 1 second |
| `SimpleDateFormat` | Formats the time as `HH:mm:ss` |
| `Calendar` | Gets the current system time |

---

## 🔄 How It Works
1. **Window Setup:** A `JFrame` window is created with a fixed size and layout using `FlowLayout`.
2. **Time Display:** A `JLabel` is added to display the time with a large font.
3. **Live Clock Update:** A `javax.swing.Timer` runs every `1000` milliseconds (1 second), triggering a method that fetches the current time using `Calendar` and formats it using `SimpleDateFormat`.
4. **Output:** The clock shows current time in the format `HH:mm:ss`, e.g., `15:46:30`.

---

## ✅ Steps to Compile & Run

### 🔹 Step 1: Save the Java file
Save the following content into a file named `DigitalClock.java`:

```java
import javax.swing.*;
import java.awt.*;
import java.text.SimpleDateFormat;
import java.util.Calendar;

public class DigitalClock extends JFrame {
    private JLabel clockLabel;

    public DigitalClock() {
        setTitle("Digital Clock");
        setSize(300, 150);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(new FlowLayout());

        clockLabel = new JLabel();
        clockLabel.setFont(new Font("Arial", Font.BOLD, 30));
        add(clockLabel);

        Timer timer = new Timer(1000, e -> updateClock());
        timer.start();

        updateClock();
        setVisible(true);
    }

    private void updateClock() {
        SimpleDateFormat sdf = new SimpleDateFormat("HH:mm:ss");
        clockLabel.setText(sdf.format(Calendar.getInstance().getTime()));
    }

    public static void main(String[] args) {
        new DigitalClock();
    }
}
```

### 🔹 Step 2: Compile
```bash
javac DigitalClock.java
```

### 🔹 Step 3: Run
```bash
java DigitalClock
```

---

## 💡 Output & Example Screenshot
A small desktop window will appear displaying the current time in digital format, updating every second:

```text
--------------------------
|       15:43:27         |
--------------------------
```

---

## 📁 GitHub Folder Structure

```text
DigitalClock/
├── DigitalClock.java       # Source code
├── README.md               # Description and setup
├── .gitignore              # (Optional) Ignore compiled files
└── LICENSE                 # (Optional) Open-source license
```

---

## 💬 Use Cases & Future Ideas
- Practice Java GUI development
- Use in basic desktop applications
- Extendable for alarms, timers, or 12-hour/24-hour toggles

---

✨ *Built with curiosity as my first step into software development. Feedback and suggestions are always welcome!*

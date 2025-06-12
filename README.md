# Digital-Clock-Display..-
📌 Project Title:

Digital Clock Using Java Swing




🎯 Objective:

To create a GUI-based digital clock using Java Swing that displays the current system time and updates every second in real-time.




🛠️ Technology Used:

Language: Java

Library: Java Swing (JFrame, JLabel, Timer)

IDE (optional): IntelliJ IDEA, Eclipse, NetBeans, or VS Code




🧱 Components Used:

Component	Purpose

JFrame	Main window container for GUI
JLabel	Displays the time in text format
Timer	Automatically updates the time every 1 second
SimpleDateFormat	Formats the time as HH:mm:ss
Calendar	Gets the current system time




🔄 How It Works:

1. Window Setup
A JFrame window is created with a fixed size and layout using FlowLayout.


2. Time Display
A JLabel is added to display the time with a large font.


3. Live Clock Update
A javax.swing.Timer runs every 1000 milliseconds (1 second), triggering a method that fetches the current time using Calendar and formats it using SimpleDateFormat.


4. Output
The clock shows current time in the format HH:mm:ss, e.g., 15:46:30.




✅ Steps to Compile & Run:

🔹 Step 1: Save the Java file

Save the following content into a file named DigitalClock.java:

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

🔹 Step 2: Compile

javac DigitalClock.java

🔹 Step 3: Run

java DigitalClock

💡 Output:

A small window will appear displaying the current time in digital format, updating every second.



📁 GitHub Folder Structure:

DigitalClock/
├── DigitalClock.java       # Source code
├── README.md               # Description and setup
├── .gitignore              # (Optional) Ignore compiled files
└── LICENSE                 # (Optional) Open-source license



📋 Example Screenshot:

Since it uses Swing, it opens a small window with a digital clock like this:

--------------------------
|       15:43:27           |
 --------------------------


 
💬 Use Cases:

Practice Java GUI development

Use in basic desktop applications

Extendable for alarms or timers

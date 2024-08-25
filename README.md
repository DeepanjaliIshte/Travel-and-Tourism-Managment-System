# Travel=and=Tourism=Managment=System

<h3>Splash </h3>

<h4>1. Splash Class (Main Class)</4>
<h6>This is the entry point of the application.</h6>

<h5>public static void main(String[] args):</h5>
<h6>This method creates an instance of SplashFrame and makes it visible.<br>
A loop animates the splash screen by gradually increasing the size of the frame.</h6>

<h5>During each iteration of the loop:</h5>
<h5>f1.setLocationRelativeTo(null):</h5> <h6>This centers the splash screen on the screen.</h6>
<h5>f1.setSize(i, i):</h5> <h6>The frame size is incremented by 10 pixels in both width and height.</h6>
<h5>f1.scaleImage(i, i): </h5><h6>This method adjusts the size of the image to match the current size of the frame.</h6>
<h5>Thread.sleep(10):</h5> <h6>This pauses the execution for 10 milliseconds, creating a smooth animation effect.</h6>

<h3>3. SplashFrame Class</h3>
<h6>This class extends JFrame and handles the splash screen's display and animation. It also implements Runnable to allow for concurrent execution.</h6>

<h5>SplashFrame() Constructor:</h5>
<h5>setLayout(new BorderLayout()):</h5><h6>This sets the layout manager of the frame to BorderLayout, which allows for easier positioning and resizing of components.</h6>
<h5>originalIcon = new ImageIcon(ClassLoader.getSystemResource("Img/splash.jpg")):</h5> <h6> This loads the image from the Img directory and creates an ImageIcon object. The ClassLoader.getSystemResource() method helps to locate the image in the classpath.</h6>
<h5>label = new JLabel(originalIcon):</h5> <h6> This creates a JLabel to display the image.</h6>
<h5>label.setHorizontalAlignment(JLabel.CENTER) and label.setVerticalAlignment(JLabel.CENTER): </h5> <h6>These methods ensure that the image is centered within the frame.</h6>
<h5>add(label, BorderLayout.CENTER): </h5> <h6>This adds the JLabel to the center of the frame, allowing it to scale properly as the frame size changes.</h6>
<h5>setUndecorated(true):</h5>  <h6>This removes the window decorations (title bar and borders), giving a cleaner look to the splash screen.</h6>
<h5>t1 = new Thread(this)and t1.start();:</h5>  <h6>These lines start a new thread that will run the run() method, allowing the splash screen to display for a set duration.</h6>

<h5>scaleImage(int width, int height) Method:</h5>
<h5>Image img = originalIcon.getImage(): </h5> <h6>This retrieves the original image from the ImageIcon.</h6>
<h5>Image scaledImg = img.getScaledInstance(width, height, Image.SCALE_SMOOTH):</h5> <h6>This scales the image to the specified width and height using Image.SCALE_SMOOTH for better quality.</h6>
<h5>ImageIcon scaledIcon = new ImageIcon(scaledImg):</h5> <h6> This creates a new ImageIcon with the scaled image.
<h5>label.setIcon(scaledIcon): <h5> <h6>This updates the JLabel with the new scaled image, so the image size always matches the frame size.

<h5>public void run() Method:</h5>
<h5>Thread.sleep(7000):</h5> <h6> This pauses the execution for 7 seconds, allowing the splash screen to be displayed for that duration.</h6>
<h5>dispose():</h5> <h6> This closes the splash screen.</h6>
<h5>Login l = new Login() and l.setVisible(true): </h5> <h6>After closing the splash screen, a new Login window is opened. (Assuming a Login class is implemented elsewhere in the application.)</h6>
------------------------------------------------------------------------------------------------------------------------------------------------------

How It Works Together:
Initialization: The Splash class initializes the splash screen (SplashFrame) and makes it visible.
Animation Loop: The main method animates the splash screen by gradually increasing the size of the frame and scaling the image to fit the new size.
Thread Execution: The SplashFrame class runs a separate thread to display the splash screen for 7 seconds before disposing of it and opening the login window.
Image Scaling: The scaleImage() method ensures that the image remains clear and properly scaled as the frame size changes during the animation.

Key Concepts:
Threading: Allows the splash screen to be displayed for a set duration without freezing the user interface.
Dynamic Image Scaling: The image size is adjusted dynamically to match the changing frame size, ensuring that it always looks good and fits within the frame.
Centering: The splash screen and image are both centered on the screen for a professional appearance.
This approach provides a smooth and visually appealing splash screen experience for your application.

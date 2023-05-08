Download Link: https://assignmentchef.com/product/solved-solved-p5mytunes
<br>
This is your final project and it’s a fun one! You will be implementing a basic iTunes &#x2122; like application with a heat map visualization that shows you which songs you play the most.

Sample myTunes GUISample myTunes GUIObjectives

Design and implement a Graphical User Interface (GUI) program in Java.Design a good user interface.Use several classes from the AWT and Swing graphics packages.Manage a grid of buttons using a 2-dimensional array.Re-use classes that you implemented previously in a new context.Apply the basics of event-driven programming using events and listeners.Getting Started

Design

Before you start writing any of the code, read through the specifications and draw a rough sketch of your GUI. We will be collecting this 2 weeks before your project is due to make sure you are on track.

sample design sketchsample layout design sketch.Label the various components in your design with the corresponding Java classes (e.g. JLabel, JList, JButton, etc.).Group your sketch into logical sections that will be implemented in the same Java container (e.g. all of the song control buttons will go in a sub-panel). Make notes on your diagram about the LayoutManager and Border style (if any) you will use for each container.Project Setup

Create a new Eclipse project for this assignment.The easiest way to import all the files into your project is to download and unzip the starter files directly into your project workspace directory (using the command-line or dolphin). The starter files are available here: http://cs.boisestate.edu/~cs121/projects/p5/stubs (You should download p5-stubs.zip).After you unzip the files into your workspace directory outside of Eclipse, go back to Eclipse and refresh your project. You should have the following files (if your setup looks different than what is shown below, you will want to fix it now before you get too far):imported filesInitial Eclipse Import.MyTunesGUI-Sample.jar: A runnable example of the project. To see the sample GUI in action, you can run the jar from the command-line using:java -jar MyTunesGUI-Sample.jarMyTunesGUI.java:The main driver class. Adds your panel to a frame and launches it.MyTunesPlayListInterface.java:The interface providing method headers for all the new methods you will need in your PlayList class to manage the songs.images/*.gif:A directory containing icons (in case you don’t want to find your own). I downloaded these from http://www.iconsdb.com.sounds/playlist.txt:A new playlist import file that contains more songs than P3.sounds/*.wav:Some cheesy sound clips (the same as in P3).Import your Song.java and PlayList.java classes from project 3 into your project.If you didn’t get these working, now is the time to get them working. Don’t be afraid to ask for help.Create MyTunesGUIPanel.java (the main panel class) in your project.At this point, your Eclipse project should have the following layout.imported filesInitial Eclipse Import.Implementation and Testing

The details of the following items are outlined in the Specification sections below. This section is intended to give you an overview of the big picture before jumping into the details.

Start by implementing the MyTunesPlayListInterface in your PlayList to make sure you have all the methods you will need to manipulate your playlist in your GUI.Then, move to your MyTunesGUIPanel and write the code to produce the GUI you sketched above.Pro tips:Working on one component at a time helps to reduce the overall complexity of this project. Don’t worry about any of the logic for now. Just get your GUI looking the way you want it. And don’t spend too much time making the layout perfect. Get everything on there and you can always go back and tweak things if you have time.

Choose good variable names! If you don’t, it can be extremely difficult to remember what everything is. If something is a JButton, put button in the name (e.g. private JButton playSongButton; ). If something is a JPanel, put panel in the name (e.g. private JPanel songControlPanel;). This will also make it easier for our tutors to help you if you get stuck.

Once you have the visual framework in place consider the listeners and how they will interact with each component in your design. Decide if you want a single event listener with a compound conditional or if you want separate listeners to handle each event.Pro tip:To make sure all of your listeners are hooked up correctly, you can just print something to the console in the action listener and make sure it prints when you interact with the component. For example, after hooking up your listener to your playSongButton, print “Play song button clicked…” in your actionPerformed method and verify that is showed up on your console. This can prevent spending hours on a bug because you forgot to add the action listener to the component.Finally, implement the playlist and song grid logic. Make sure you are testing early and often!Ensure you have the basic functionality implemented before improving or adding to your MyTunes. Extra credit will not make up for problems with the basic functionality!Specification

Step 0: MyTunesPlayListInterfaceStep 1: User Interface DesignStep 2: Loading the PlayListStep 3: Manipulating the PlayListStep 4: Playing SongsStep 5: Music SquareExtra CreditProject files

For this assignment you are going to implement the MyTunesGUIPanel which is the class that will extend JPanel and contains the GUI setup and logic.

You should be able to develop this program incrementally in such a way that you can turn in a program that runs even if you don’t succeed in implementing all the specified functionality.

Step 0: MyTunesPlayListInterface

PlayList.java

You will need to modify your existing PlayList class from project 3.

First, modify your PlayList class header so it implements the MyTunesPlayListInterface.

public class PlayList implements MyTunesPlayListInterfaceMake sure to stub out all the methods (you can use the Eclipse auto-fix suggestion).

You must load a playlist from the playlist.txt file. Add an overloaded constructor to your PlayList class that takes in a File as an argument and reads in the song data from the provided text file, adding each song to the playlist.

Hint: Most of this logic was provided in the loadPlaylist(String filename) method in Jukebox.java, you just need to move the code into a constructor and instead of creating a new PlayList instance, you will just add the songs using this.addSong(song)./*** Creates a play list from the song data in the given file.* @param file The file containing the song data.*/public PlayList(File file){

}Step 1: User Interface Design

The following components are required. Your layout doesn’t have to look like the one we provided. Be creative and have fun with it! This should all be done in MyTunesGUI and MyTunesGUIPanel.

Labels for the name of the playlist, the number of songs in the playlist, and the total play time of the playlist.A button to play the entire playlist (from start to finish).The list of songs in the playlist (as a JList).Buttons for moving songs up/down the list.Buttons to add and remove songs from the playlist.Buttons to control the play back of a song in the playlist (e.g. play previous, play next, play/stop current song).The name and artist of the song that is currently playing should be displayed somewhere.A grid of buttons providing a visualization of the play list. Eventually, these buttons will change colors based on the number of times a song has been played creating a heat map of your play list.Here are some helpful examples for this step. Don’t just look at them on the GitHub page. Run them in Eclipse. You should have all the chap06 examples checked out already. (Also, these aren’t necessarily the only examples that will be helpful, but just a list to help you sort through them).

LayoutDemo.javaJListDemo.java (and corresponding JListDemoPanel.java )TwoDColorChooser.javaYour PhotoAlbumGUI lab files.After this step, your GUI may look something like this:

Sample GUI Prototype.Sample GUI Prototype.Step 2: Loading the PlayList

The next task is to get the songs loaded into your JList. To do this, you will first need to provide a way to convert your ArrayList of songs into an array of songs (Song[]).Use your overloaded PlayList(File file) in your MyTunesGUIPanel to create the underlying playlist data.

Implement the public Song[] getSongArray() method provided in the MyTunesPlayListInterface and call this from your GUI to get the array of songs.

Add the songs from the playlist into your JList (as demonstrated in the PhotoAlbumGUI lab).

This is similar to what you did in the PhotoAlbum class for the PhotoAlbumGUI lab. You may even want to consider putting this logic in a method (as shown in the lab) because you will need to sync JList data later on too.Update the play list name, the number of songs and total play time labels with the correct values.Keep in mind that you will need to update these labels every time the PlayList changes.Implement a ListSelectionListener for your JList and print the title and artist of the song that is selected in the JList to make sure it is working. These are just debug statements, you will add play functionality later.Yet again, similar to what you did with the preview of your PhotoAlbumGUI lab.Don’t worry about playing the songs for now.Step 3: Manipulating the PlayList

Now, you will add action listeners to all your buttons. You can choose to use a single listener for all of your buttons using conditionals to check the source, or you can create different action listeners for each button. It’s up to you. There are advantages and disadvantages to both ways.

Implement the action listeners for switching the song order of your playlist. When you switch the order, you aren’t actually changing the order in the JList (this isn’t possible without some major code going on), you are changing the order in your PlayList class and resetting the list data with the contents of the modified playlist. You may find this example helpful (it’s the same one that was given in the PhotoAlbumGUI lab.JListDemo.java (The driver class).JListDemoPanel.java (The JPanel GUI class).To move songs in the PlayList, implement the moveUp(int index) and moveDown(int index) methods provided in the MyTunesPlayListInterface and call these from your GUI when the buttons are clicked.

Implement the action listener for your “Add Song” button.

When the button is clicked, it should pop up a JOptionPane asking for the song information. When the user clicks OK, the text in the JTextFields should be read and used to create a new Song.The song must be added to the playlist and the JList should be synced with the new array.Ideally, you would want to use a JFileChooser to let the user select a file from the file system and validate that the user entered valid information. You can have them enter a filename string and assume they entered the correct data for now and come back to this if you have time.Here are some JOptionPane/FileChooser examplesJOptionPaneDemo.java (and corresponding JOptionPaneDemoPanel.javaFileChooser.javaImplement the action listener for your “Remove Song” button.

When the button is clicked, it should pop up a JOptionPane asking if they are sure they want to remove the song.If they click “Yes”, the song must be removed from the playlist and the JList should be synced with the new array.Make sure you are updating the number of songs and total playtime of the playlist each time you add/remove a song from the playlist.Step 4: Playing Songs

Important: You will need to modify your existing playSong method to stop the currently playing song before playing the next (if you don’t…you will know…what an awful noise!). If you haven’t already, implement the stop() and playSong(Song song) methods outlined in the MyTunesPlayListInterface.The song currently selected in the song JList should play when the user clicks the play button.When the user clicks the next button, the current song should be stopped and the next song in the list should start playing.When the user clicks the previous button, the previous song should be stopped and the previous song in the list should start playing.You will need to use a Timer (from the javax.swing package) to play each song for the specified amount of time (e.g. song.getPlayTime()). See examplesTimerDemo.java (and corresponding TimerDemoPanel.java). – Shows how to start/stop a timer and handle an event when the timer fires.TimerDemoCooler.java (and corresponding TimerDemoCoolerPanel.java). – Shows how to start/stop/reset timer and how to handle a timer event to update the GUI every second. (Useful if you want to display the number of seconds that have passed since the song started playing. Not required.).Make sure you are updating the Playing Now song information when you start/stop playing a song.Step 5: Music Square

The music square was inspired by Samsung’s Music Square app. The original Music Square requires classification and sorting, so we decided it was a little too complex for this class, but we went with something similar — a 2 dimensional grid visualization of the songs in your playlist (added in the order of the playlist) with a heat map showing which songs are played most often.

The size of the grid is dependent on the number of songs in your playlist.If you have 25 songs, your grid should be 5 x 5.If you have 100 songs, your grid should be 10 x 10.If you have 20 songs (a non-square number), your grid should be 5 x 5, with the remaining 5 songs repeated in the last row.Implement the public Song[][] getMusicSquare() method in your PlayList class (as described in the MyTunesPlayListInterface javadoc comment. Use this method to get the 2D array of songs needed for your grid of buttons.The button should display the name of the song.The song square should be updated as songs are added/removed from the playlist and when songs are moved up/down the order of the playlist.To see this in action, run the sample jar and delete 9 of the songs. The square should switch from 5 x 5 to 4 x 4.See GameBoard.java (and corresponding GameBoardPanel.java). – Shows how to replace an existing panel with a new one.When the button is clicked, the song should play.Each time a song is played (from the music square or via the play button), the button corresponding to the played song in the music square should be updated with the new heat map color. Here is a method you can use to get the color based on the number of times the song has been played./*** Given the number of times a song has been played, this method will* return a corresponding heat map color.** Sample Usage: Color color = getHeatMapColor(song.getTimesPlayed());** This algorithm was borrowed from:* http://www.andrewnoske.com/wiki/Code_-_heatmaps_and_color_gradients** @param plays The number of times the song that you want the color for has been played.* @return The color to be used for your heat map.*/private Color getHeatMapColor(int plays){double minPlays = 0, maxPlays = MAX_PLAYS; // upper/lower boundsdouble value = (plays – minPlays) / (maxPlays – minPlays); // normalize play count

// The range of colors our heat map will pass through. This can be modified if you// want a different color scheme.Color[] colors = { Color.CYAN, Color.GREEN, Color.YELLOW, Color.ORANGE, Color.RED };int index1, index2; // Our color will lie between these two colors.float dist = 0; // Distance between “index1” and “index2” where our value is.

if (value &lt;= 0) {index1 = index2 = 0;} else if (value = 1) {index1 = index2 = colors.length – 1;} else {value = value * (colors.length – 1);index1 = (int) Math.floor(value); // Our desired color will be after this index.index2 = index1 + 1; // … and before this index (inclusive).dist = (float) value – index1; // Distance between the two indexes (0-1).}

int r = (int)((colors[index2].getRed() – colors[index1].getRed()) * dist)+ colors[index1].getRed();int g = (int)((colors[index2].getGreen() – colors[index1].getGreen()) * dist)+ colors[index1].getGreen();int b = (int)((colors[index2].getBlue() – colors[index1].getBlue()) * dist)+ colors[index1].getBlue();

return new Color(r, g, b);}Extra Credit (Up to 10 points)

Ensure you have the basic functionality implemented before improving or adding to the gui. Extra credit will not make up for problems with the basic functionality!

Sort by artist/title buttons. Sorts playlist and updates GUI. (Heads up! It is pretty challenging to sort custom objects (aka Songs)). (5 points)Shuffle/Repeat playlist (5 points).Save/Load playlist to/from file (5 points).Heat map gradient bar (3 points).Anything else pre-approved by your instructor. Make sure you check first!Testing

You must test your program thoroughly before submitting it. We will be using similar testing strategies when we grade your program, so you should have a good idea whether or not your code will pass our tests before submitting.

Submitting Your Project

Documentation

Javadoc Comments

If you haven’t already, add javadoc comments to your program. They should be located immediately before the class header and before each method. If you forgot how to do this, go look at the Documenting Your Program section from lab.

Have a class javadoc comment before the class.Your class comment must include the @author tag at the end of the comment. This will list you as the author of your software when you create your documentation.Have javadoc comments before every method that you wrote. Comments must include @param and @return tags as appropriate.To build and view your comments, run the following commands.javadoc -author -d doc *.javagoogle-chrome doc/index.htmlREADME

Include a plain-text file called README that describes your program and how to use it. Expected formatting and content are described in README_TEMPLATE. See README_EXAMPLE for an example.

Submission

You will follow the same process for submitting each project.

Open a console and navigate to the project directory containing your source files,Remove all the .class files using the command, rm *.class.In the same directory, execute the submit command for your section as shown in the following table.Look for the success message and timestamp. If you don’t see a success message and timestamp, make sure the submit command you used is EXACTLY as shown.Required Source FilesRequired files (be sure the names match what is here exactly):MyTunesGUI.java (main class)MyTunesGUIPanel.javaMyTunesPlayListInterface.javaPlayList.javaSong.javaREADMEAny other files necessary to compile and run your programSection Instructor Submit Command1 Luke Hindman (TuTh 1:30 – 2:45) submit lhindman cs121-1 p52 Greg Andersen (TuTh 9:00 – 10:15) submit gandersen cs121-2 p53 Luke Hindman (TuTh 10:30 – 11:45) submit lhindman cs121-3 p54 Marissa Schmidt (TuTh 4:30 – 5:45) submit marissa cs121-4 p55 Jerry Fails (TuTh 1:30 – 2:45) submit jfails cs121-5 p5After submitting, you may check your submission using the “check” command. In the example below, replace &lt;instructor with your instructor and &lt;x with your section.

submit -check &lt;instructor &lt;section p5
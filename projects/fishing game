---
layout: project
type: project
image: imageforfishfishfish.png
title: "fish, fish, fish"
date: 2024
published: true
labels:
  - Lisp
  - GitHub
summary: "A text game that I developed for ICS  241."
---

<img class="img-fluid" src="../img/cotton/cotton-header.png">

This game is that yyou can actualy experience real fishing with traps etc....
Try catch as many as fish you can!!



-actual code fpr trap function.-

public class fishingTrap extends JFrame implements KeyListener, FishingTool{
   private String sequence = "";
   private int revolutions = 0;
   private int neededRevolutions;
   private String targetSequence;
   private boolean conditionMet = false;

   public fishingTrap(String target, int numRevolutions) {
      super("Key Sequence Listener");
      this.targetSequence = target;
      this.neededRevolutions = numRevolutions;
      // Setup the JFrame
      setSize(400, 200);
      setLocationRelativeTo(null);  // Center the window
                                    // Create a text area to display instructions
      JTextArea textArea = new JTextArea();
      String display = "Type the Sequence '";
      for (char c : targetSequence.toCharArray()) {
         display = display + c + " ";
      }
      display = display + "' on your keyboard";
      textArea.setText(display);
      textArea.setEditable(false);
      // Add the text area to the frame
      add(textArea);
      // Add key listener to the text area
      textArea.addKeyListener(this);
   }

   @Override
   public void keyTyped(KeyEvent e) {
      // Append each key typed to the sequence
      sequence += e.getKeyChar();
      // Check if the last 5 characters match the target sequence
      if (sequence.length() >= this.targetSequence.length() && sequence.substring(sequence.length() - this.targetSequence.length()).equals(targetSequence)) {
         System.out.println(revolutions + " YESSIR");
         revolutions++;
         sequence = "";  // Reset sequence after detection
         if (revolutions == neededRevolutions) {
            conditionMet = true;
            clearConsole();
         }
      }
   }

   @Override
   public void keyPressed(KeyEvent e) {
      // Implementation not needed for this example
   }

   @Override
   public void keyReleased(KeyEvent e) {
      // Implementation not needed for this example
   }

   public boolean isConditionMet() {
      return conditionMet;
   }

   public static void clearConsole() {
      try {
         String os = System.getProperty("os.name").toLowerCase();

         if (os.contains("windows")) {
            // Clears the console for Windows operating system
            new ProcessBuilder("cmd", "/c", "cls").inheritIO().start().waitFor();
         } else {
            // Clears the console for Unix/Linux/Mac operating systems
            new ProcessBuilder("clear").inheritIO().start().waitFor();
         }
      } catch (Exception e) {
         System.out.println("Error occurred while clearing the screen: " + e.getMessage());
      }
   }
}

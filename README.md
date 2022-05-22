import java.awt.event.*;
import java.awt.Robot;
import java.awt.MouseInfo;

public class Test {
 public static void main(String args[]) {
  Robot bot = null;
  try {
   bot = new Robot();
  } catch (Exception failed) {
   System.err.print("Failed instantiating Robot: " + failed);
  }
  int mask = InputEvent.BUTTON1_DOWN_MASK;
  System.out.println("Mouse Move, mouse click,mouse wheel move up and down,enter key ---->Repeat after 30 secs...");
  System.out.print("Started.Press <Cntrl>+C here to exit.");

  while(true){
  bot.mouseMove((Integer)MouseInfo.getPointerInfo().getLocation().x+1, (Integer)MouseInfo.getPointerInfo().getLocation().y+1);
  bot.mouseMove((Integer)MouseInfo.getPointerInfo().getLocation().x-1, (Integer)MouseInfo.getPointerInfo().getLocation().y-1);

  bot.mousePress(mask);
  bot.mouseRelease(mask);
  bot.mouseWheel(5);
  bot.mouseWheel(-5);
  bot.keyPress( KeyEvent.VK_ENTER);
  bot.setAutoDelay(1000*30);
  System.out.print(".");
  }
 }
}

# QUEUE

package MyPackage; 
import java.util.Scanner;
public class Main { public static void main(String[]
args) { Scanner sc = new Scanner(System.in); int n = Integer.parseInt(sc.nextLine()); Queue q =
new Queue();
for (int i = 0; i < n; i++) {
String command = sc.nextLine().trim();
if (command.startsWith("insert(")) {
String numStr = command.substring(command.indexOf(",") + 1,
command.indexOf(")")).trim();
int x = Integer.parseInt(numStr);
q.insert(x);
} else if (command.startsWith("x=remove(")) {
q.remove();
} else if (command.startsWith("empty(")) {
q.empty();
} else if (command.equals("DISPLAY")) {
q.display();
}
}
sc.close();
}
}
package MyPackage;
import java.util.LinkedList; 
public class Queue {
private LinkedList<Integer> items;
public Queue() {
items = new LinkedList<>();
}
public void insert(int x) {
items.addLast(x);
}
public void remove() {
if (items.isEmpty()) {
System.out.println("Queue Underflow");
} else {
System.out.println(items.removeFirst());
}
}
public void empty() {
System.out.println(items.isEmpty() ? "true" : "false");
}
public void display() {
if (items.isEmpty()) {
System.out.println();
} else {
for (int i = 0; i < items.size(); i++) {
System.out.print(items.get(i));
if (i < items.size() - 1) System.out.print(" ");
}
System.out.println();
}
}
}

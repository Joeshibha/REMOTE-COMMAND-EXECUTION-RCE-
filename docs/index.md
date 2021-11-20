## Welcome to GitHub Pages

IMPLEMENTATION OF REMOTE COMMAND EXECUTION (RCE)

AIM

To implement Remote Command Execution(RCE).

ALGORITHM

CLIENT SIDE

1. Establish a connection between the Client and Server.
Socket client=new Socket("127.0.0.1",6555);
2. Create instances for input and output streams.
Print Stream ps=new Print Stream(client.getOutputStream());
3. BufferedReaderbr=newBufferedReader(newInputStreamReader(System.in));
4. Enter the command in Client Window.
Send the message to its output
str=br.readLine();
ps.println(str);

SERVER SIDE

1. Accept the connection request by the client.
ServerSocket server=new ServerSocket(6555);
Sockets=server.accept();
2. Getthe IPaddressfromitsinputstream.
BufferedReaderbr1=newBufferedReader(newInputStreamReader(s.getInputStream()));
ip=br1.readLine();
3. During runtime execute the process
Runtime r=Runtime.getRuntime();
Process p=r.exec(str);

CLIENT PROGRAM

import java.io.*;
import java.net.*;
class clientRCE
{
public static void main(String args[]) throws IOException
{
try
{
String str;Socket client=new Socket("127.0.0.1",6555);
PrintStream ps=new PrintStream(client.getOutputStream());
BufferedReader br=new BufferedReader(new InputStreamReader(System.in));
System.out.println("\t\t\t\tCLIENT WINDOW\n\n\t\tEnter TheCommand:");
str=br.readLine();
ps.println(str);
}
catch(IOException e)
{
System.out.println("Error"+e); }
}
}

SERVER PROGRAM

import java.io.*;
import java.net.*;
class serverRCE
{
public static void main(String args[]) throws IOException
{
 try
{
String str;
ServerSocket server=new ServerSocket(6555);
Socket s=server.accept();
BufferedReader br=new BufferedReader(new InputStreamReader(s.getInputStream()));
str=br.readLine();
Runtime r=Runtime.getRuntime();
Process p=r.exec(str);
}
catch(IOException e)
{
System.out.println("Error"+e);
}
}
}

OUTPUT

![image](https://user-images.githubusercontent.com/67230459/142728481-66ac1c74-1b66-4ea8-905b-2d4de63001e8.png)

![image](https://user-images.githubusercontent.com/67230459/142728487-e1c35074-b286-400a-9aff-cab0a787e900.png)

 
RESULT

Thus the implementation of RCE is done & executed and then published in github successfully.


### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.

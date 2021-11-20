# REMOTE-COMMAND-EXECUTION-RCE-
To implement Remote Command Execution(RCE)

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

import java.io.*;
import java.net.*;
import java.util.zip.*;
public class CheckServer {
public static void main(String[] args) throws Exception {
ServerSocket serverSocket = new ServerSocket(1234);
System.out.println("Server started");
while (true) {
Socket clientSocket = serverSocket.accept();
System.out.println("Client connected: " + clientSocket.getInetAddress().getHostAddress());
InputStream inputStream = clientSocket.getInputStream();
BufferedInputStream bufferedInputStream = new BufferedInputStream(inputStream);
byte[] data = bufferedInputStream.readAllBytes();
Checksum checksum = new CRC32();
checksum.update(data, 0, data.length);
long checksumValue = checksum.getValue();
System.out.println("Checksum value of received data: " + checksumValue);
FileOutputStream fileOutputStream = new FileOutputStream("receivedData.txt");
fileOutputStream.write(data);
fileOutputStream.close();
clientSocket.close();
}
}
}

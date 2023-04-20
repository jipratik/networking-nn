import java.io.*;
import java.net.*;
import java.util.zip.*;
public class CheckClient {
public static void main(String[] args) throws Exception {
Socket socket = new Socket("localhost" ,1234);
System.out.println("Connected to server");
OutputStream outputStream = socket.getOutputStream();
BufferedOutputStream bufferedOutputStream = new BufferedOutputStream(outputStream);
FileInputStream fileInputStream = new FileInputStream("dataToSend.txt");
byte[] data = fileInputStream.readAllBytes();
fileInputStream.close();
bufferedOutputStream.write(data);
bufferedOutputStream.flush();
Checksum checksum = new CRC32();
checksum.update(data, 0, data.length);
long checksumValue = checksum.getValue();
System.out.println("Checksum value of sent data: " + checksumValue);
socket.close();
}
}

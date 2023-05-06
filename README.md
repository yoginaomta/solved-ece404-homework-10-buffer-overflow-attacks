Download Link: https://assignmentchef.com/product/solved-ece404-homework-10-buffer-overflow-attacks
<br>
<h1></h1>

In the Homework section of the course webpage, you will find two socket programs written in C. One of them acts as a server and the other as a client. Your task is to launch an attack such that you execute the “secret” function in the server side code by using the client program to send a carefully crafted string to the server. <em>Then</em>, show how you would fix server.c to prevent such a buffer overflow attack.

<ul>

 <li>If using gcc on your Linux machine, compile the server and client programs with the ’-fnostack-protector’ option. Refer to pages 36-37 of Lecture 21 for more details. If you wish, you can also use the Tiny C compiler tcc that can be used without options.</li>

 <li>You can test the programs with two different shell terminals: one terminal for a server and the other terminal for a client. You can also run the server on a Purdue ECN machine using a high numbered port like 7777 and the client on your own laptop.</li>

 <li>Use gdb to determine how you can develop a string to send (using the client program) to the server program and trigger the execution of secretFunction(). Refer to lecture 21.6 for more details on how to do this. Here are some things to keep in mind when creating this string:

  <ol>

   <li>While you send the data with the client program, you will have to run the server program with gdb to determine the buffer overflow string to use.</li>

   <li>When sending the string to the server program, note that you can send ASCII characters as well as hexadecimal-format bytes. You can send, for example, the hex byte 0xAD using the format xAD.</li>

   <li>As in the lecture notes, you will need to reverse the order of addresses sent to deal with big endian-little endian conversion problems.</li>

  </ol></li>

 <li>You may need to turn off ASLR on your operating system for the attack to work properly.</li>

 <li>After you have crafted your buffer overflow string and triggered the execution of secretFunction(), modify server.c to remove the buffer overflow vulnerability.</li>

 <li><strong>Include comments </strong>in the code explaining what the vulnerability was and how you fixed it.</li>

</ul>
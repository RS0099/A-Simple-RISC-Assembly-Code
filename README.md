# A-Simple-RISC-Assembly-Code
Assembly code to find Ramanujan Number -1729
Question )Write a SimpleRisc assembly program to find the Ramanujan number, the smallest number that is a sum of two cubes in two different ways. 

Ans)
mov r0,1  //  int r0==num=1;

.l1:
mov r1,0  //int r1==count=0;
mov r3,0   //r3==i==0 ;

.l2:
add r3,r3,1
mul r4,r3,r3
mul r4,r4,r3
com r4,r0     //compare i*i*i<=num
bgt.l5           //if i^3>num goto l4
mov r5,r3    //int j==r5==i

.l3:
add r5,r5,1
mul r6,r5,r5
mul r6,r6,r5  
com r6,r0
bgt.l2
add r7,r4,r6  // add i*i*i+j*j*j
com r7,r0
beq.l4
jmp.l3

.l4:
add r1,r1,1
jmp.l3

.l5:
com r1,2
beq.l7   // if count is 2 , we got the number
add r0,r0,1
jmp.l1

.l7:
//print the number stored in r0
ret  //return

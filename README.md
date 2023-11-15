
<h1>Mini Project Design</h1>

# Traffic Light Controller used at intersection of a busy road and street road

<!-- First Section -->
## Team Details

<details>
  <summary>Detail</summary>

  > Semester: 3rd Sem B. Tech. CSE

  > Section: S1

Team Members :
<h5>1.221CS110 - A. Yoga Anil Kumar - Anumola Yoga AnilKumar.221cs110@nitk.edu.in - 7013014805 </h5>
<h5>2.221CS161 - Umang Agarwal      - umangagarwal.221cs161@nitk.edu.in           -9958794560 </h5>
<h5>3.221CS162 - V.Taraka Ravindra  - tarakaravindra.221cs162@nitk.edu.in        - 7569248124  </h5>
</details>

<!-- Second Section -->
## Abstract
<details>
  <summary>Detail</summary>
  
  <p>
  The simple traffic light controller design project was introduced to alleviate this shortcoming and gain experience in solving implementation and interfacing problems of a modern digital system. we implement a fully functional traffic signal controller for a four-way intersection between a busy road and village road, where less traffic is present. Intersection is complete with sensors to detect the presence of vehicles waiting at or approaching the inter-section .</p>
  <p>These include HDL for modeling and finite state machines, and serial communication. Traffic lights, also known as traffic lamps, traffic signals, stoplight, stop-and-go lights semaphore or robots, are signaling devices positioned at pedestrian crossings, road intersections, and other locations to control competing flows of traffic. Traffic lights have installed in most cities around the world to control the flow of traffic.It assign the right of way to road users by the use of lights in standard colors (Red - Yellow - Green), using a universal color code (and a precise sequence, for color blind). It requires us to develop a state machine based controller for traffic signals at a four-way 
</p>
<img width="428" alt="image" src="https://github.com/Ravindra162/Traffic-Light-Controller-using-logisim-and-verilog/assets/121024571/ad6b1e87-56c2-4750-878d-f4b00c96349c">
</details>
<!-- Third Section -->
<h2>Working  : </h2>
<details>
  <summary>Detail</summary>
<h3>Description : </h3>
<p>
 As we know,Traffic lights are an essential part of road safety and help regulate the flow of traffic at intersections.We are implementing this project based on “Finite State Machine(FSM)” concepts to meet the requirements. Our project basically controls the traffic lights between intersection of a very Busy road (eg : highway road) and a normal road (eg : street road) with certain time delays for each of the color to change. 
</p>
<p>
 The implementation of a Finite State Machine (FSM) for traffic control at the intersection of a busy highway and a quieter street road demonstrates a systematic and efficient approach to managing traffic flow while prioritizing safety. This system is designed to enhance road safety and optimize traffic management.
</p>
<p>
 In this FSM-based system, the primary objective is to ensure the smooth flow of traffic along the highway road. To accomplish this, the green signal remains active by default, prioritizing the highway road. However, the installation of sensors at the entrance of the street road allows the system to detect the presence of vehicles. When a vehicle is sensed, the sensor triggers a state transition, and the green signal on the highway side is temporarily interrupted.
</p>
<p>
 During this transition, the green light on the highway side switches to red, allowing the vehicle on the street road to access the intersection safely. After a predetermined time delay, the green signal returns to the highway road, resuming the priority flow. This intelligent traffic control system efficiently balances the needs of both the busy highway and the village road, ensuring safety and optimizing traffic flow at the intersection.
</p>
<p>
 Incorporating timers for each traffic light phase is a crucial aspect of your traffic control system, enhancing its precision and safety. The specific timing intervals you've mentioned are well-suited to maintain efficient traffic flow and minimize congestion at the intersection.
 <ul>
    <li><h4>Green Light for Highway (16 seconds): </h4>Allowing a 16-second green light for the busy highway road ensures that traffic on this route experiences extended periods of priority. This long duration reduces the frequency of traffic light transitions, promoting smoother traffic flow and reducing the potential for congestion.</li>
  <li><h4>Green Light for Street Road (8 seconds): </h4>With an 8-second green light for the street road, vehicles from the quieter road have a brief but adequate window of time to enter the intersection when the sensor is triggered. This timing optimizes the throughput for the village road without causing excessive delays for highway traffic.</li>
  <li><h4>Yellow Light (4 seconds): </h4>The 4-second yellow light phase serves as a crucial safety buffer between the green and red light transitions. It signals to all approaching vehicles that a change in traffic conditions is imminent, allowing them to prepare to stop safely. This yellow phase is especially important at such a high-traffic intersection, where sudden stops could lead to accidents.</li>
 </ul>
</p>
<p>
 Busy road is considered as North-South road and Street road is considered as East-west road. We defined four states named S0,S1,S2,S3 in our Finite State Machine. Each State has a certain time delays from moving to another state. As per the FSM below we want to change the states. Using d-flip flops we can achieve it.                       
</p>
<p>
 Let us say S1 and S0 represents bits of my present state and A and B represents bits of my Future state, and T be the timer for each of the states. Consider the following truth table. 
</p>
<h4>Functional Tables</h4>
<img width="513" alt="Screenshot 2023-10-25 164448" src="https://github.com/Ravindra162/Traffic-Light-Controller-using-logisim-and-verilog/assets/121024571/3f2b1c55-ba85-4628-bd3b-ef844d7e8bae">
<p>
 Using K-map we can get the expression for A and B. Our expression’s are :
A = S1’ S0 T + S1 S0’ + S1 T’      <br>             B = S0’ T + S0 T’ = S0 ^  T<br>
Each state implies to 6 outputs such as Red light in North-south road (Busy road) as Rns<br>
                                                                       Yellow light in North-South road as Yns
                                                                        Green light in North-South road as Gns
                                                                        Red light in East-West road (street road) as Rew
                                                                       Yellow light in East-West road as Yns
                                                                        Green light in East-West road as Gns

</p>
<img width="529" alt="Screenshot 2023-10-25 164500" src="https://github.com/Ravindra162/Traffic-Light-Controller-using-logisim-and-verilog/assets/121024571/7d42ef2f-b3e1-45ab-96a6-58684886c3a9">
<p>
 Using K-map we can get the expression for Rns, Yns, Gns, Rew, Yew and Gew. Our expression’s are :<br>
Rns = S1<br>
Yns = S1’  S0 <br>
Gns = S1’  S0’ <br>
Rew = S1’ <br>
Yew = S0 S1 <br>
Gew = S1 S0’ <br>
</p>
<img width="536" alt="Screenshot 2023-10-25 164537" src="https://github.com/Ravindra162/Traffic-Light-Controller-using-logisim-and-verilog/assets/121024571/5eadfa59-6648-43e6-89d8-d13a9ae494d4">
<h3>Timers Used : </h3>
<p>
 We used a timing sequence of (if a vehicle present on the street road) the red signal in east-west road or green in the north-south road remains for 16 seconds in the Hardware part (as per convinience of usage of gates) where as 32 seconds in the verilog code. Yellow remains for 4 seconds and Green light on the  street road remains for 8 seconds (in   hardware part (logisim)) and 16 seconds in the verilog code. In the hardware part , we implement showing the timers using 7 segment displays using counters.
</p>
<h3>7-seg Display</h3>
<img width="442" alt="image" src="https://github.com/Ravindra162/Traffic-Light-Controller-using-logisim-and-verilog/assets/121024571/12dc708e-05b2-4fcb-a493-b79ff697a78e">

</details>

<!-- Fourth Section -->
## Logisim Circuit Diagram
<details>
  <summary>Detail</summary>
<img width="513" alt="Screenshot 2023-10-25 170032" src="https://github.com/Ravindra162/Traffic-Light-Controller-using-logisim-and-verilog/assets/121024571/0f7186de-04e7-4bbf-b344-cec38386db60">
<h4>32-bit counter : </h4>
<img width="553" alt="Screenshot 2023-10-25 170047" src="https://github.com/Ravindra162/Traffic-Light-Controller-using-logisim-and-verilog/assets/121024571/221870d8-d6b4-4fe8-9e60-9a18e3c4eae9">
<h4>Main component : </h4>
<img width="579" alt="Screenshot 2023-10-25 170054" src="https://github.com/Ravindra162/Traffic-Light-Controller-using-logisim-and-verilog/assets/121024571/fab920ac-b4b1-4f0f-a82e-358380e716ea">
<h4>2bit number on 7-segment display</h4>
<img width="479" alt="Screenshot 2023-10-25 170104" src="https://github.com/Ravindra162/Traffic-Light-Controller-using-logisim-and-verilog/assets/121024571/d1eb205d-f064-4f7a-beff-727b50b45774">
</details>

<!-- Fifth Section -->
## Verilog Code
<details>
  <summary>Detail</summary>
 
`timescale 1ns / 1ps

module Traffic
(
  input [4:0] nsCounter,
  input [3:0] ewCounter,
  input [1:0] yellowCounter,
  input NS_VEHICLE_DETECT,
  input EW_VEHICLE_DETECT,
  output reg NS_RED,
  output reg NS_YELLOW,
  output reg NS_GREEN,
  output reg EW_RED,
  output reg EW_YELLOW,
  output reg EW_GREEN
);

  // Sets the start state at: 001100
  initial begin
    NS_RED <= 0;
    NS_YELLOW <= 0;
    NS_GREEN <= 1;
    EW_RED <= 1;
    EW_YELLOW <= 0;
    EW_GREEN <= 0;
  end

  always @ (nsCounter) begin
  	// Sets the start state at: 010100
    if (nsCounter == 31 & EW_VEHICLE_DETECT & NS_GREEN) begin
       NS_RED <= 0;
       NS_YELLOW <= 1;
       NS_GREEN <= 0;
       EW_RED <= 1;
       EW_YELLOW <= 0;
       EW_GREEN <= 0;
    end
  end

  // Sets the start state at: 100010
  always @ (ewCounter) begin
    if (ewCounter == 15 & EW_GREEN) begin
       NS_RED <= 1;
       NS_YELLOW <= 0;
       NS_GREEN <= 0;
       EW_RED <= 0;
       EW_YELLOW <= 1;
       EW_GREEN <= 0;
    end
  end

  // Sets the start state at: 001100
  always @ (yellowCounter) begin
    if (yellowCounter == 3 & NS_YELLOW) begin
       NS_RED <= 1;
       NS_YELLOW <= 0;
       NS_GREEN <= 0;
       EW_RED <= 0;
       EW_YELLOW <= 0;
       EW_GREEN <= 1;
    end
 // Sets the start state at: 100001
    if (yellowCounter == 3 & EW_YELLOW) begin
       NS_RED <= 0;
       NS_YELLOW <= 0;
       NS_GREEN <= 1;
       EW_RED <= 1;
       EW_YELLOW <= 0;
       EW_GREEN <= 0;
    end
  end
endmodule


/*
    A Counter for the North-South Traffic Light
    Counts from 0-31
*/
module nsCounter
(
    input clk,
    output [4:0] count
);

  wire clk;
  reg[4:0] count;

  initial
    	count = 0;

  always @ ( negedge clk )
    		count[0] <= ~count[0];

  always @ ( negedge count[0] )
    		count[1] <= ~count[1];

  always @ ( negedge count[1] )
    		count[2] <= ~count[2];

  always @ ( negedge count[2] )
    		count[3] <= ~count[3];

  always @ ( negedge count[3] )
    		count[4] <= ~count[4];

endmodule


/*
    A Counter for the East-West Traffic Light
    Counts from 0-15
*/
module ewCounter
(
    input clk,
    output [3:0] count
);

  wire clk;
  reg[3:0] count;

  initial
    	count = 0;

  always @ ( negedge clk )
    		count[0] <= ~count[0];

  always @ ( negedge count[0] )
    		count[1] <= ~count[1];

  always @ ( negedge count[1] )
    		count[2] <= ~count[2];

  always @ ( negedge count[2] )
    		count[3] <= ~count[3];

endmodule


/*
    A Counter for the common yellow Traffic Light
    Counts from 0-3
*/
module yellowCounter
(
  input clk,
 	output [1:0] count
);

  wire clk;
  reg[1:0] count;

  initial
    	count = 0;

  always @ ( negedge clk )
    		count[0] <= ~count[0];

  always @ ( negedge count[0] )
    		count[1] <= ~count[1];

endmodule
`include"Traffic_eng312_proj3.v"
module Traffic_Test_1;

  // Inputs
  reg NS_VEHICLE_DETECT;
  reg EW_VEHICLE_DETECT;

  // Outputs
  wire NS_RED;
  wire NS_YELLOW;
  wire NS_GREEN;
  wire EW_RED;
  wire EW_YELLOW;
  wire EW_GREEN;

  // Clock
  reg clk;

  // Counters
  wire[4:0] count1;
  wire[3:0] count2;
  wire[1:0] count3;

  // Counter Modules
  nsCounter clock1(clk, count1); 	 // Count a total of 32 seconds
  ewCounter clock2(clk, count2); 	 // Counts a total of 16 seconds
  yellowCounter clock3(clk, count3); // Counts a total of 4 seconds

  // Main Traffic Module
  Traffic CORE (count1, count2, count3, NS_VEHICLE_DETECT, EW_VEHICLE_DETECT, NS_RED, NS_YELLOW, NS_GREEN, EW_RED, EW_YELLOW, EW_GREEN);

  initial begin

    clk = 0;
   
   
    $dumpfile("Traffic_test_1.vcd");
    $dumpvars(0,Traffic_Test_1);
    $display("  NS | EW ");
    $display("R Y G R Y G ");
    $monitor("%h %h %h %h %h %h", NS_RED, NS_YELLOW, NS_GREEN, EW_RED, EW_YELLOW, EW_GREEN);
     #10 NS_VEHICLE_DETECT = 0;#10 EW_VEHICLE_DETECT = 0;
     #10 NS_VEHICLE_DETECT = 0;#10 EW_VEHICLE_DETECT = 1;
     #10 NS_VEHICLE_DETECT = 0;#10 EW_VEHICLE_DETECT = 1;
     #10 NS_VEHICLE_DETECT = 0;#10 EW_VEHICLE_DETECT = 0;
     #10 NS_VEHICLE_DETECT = 0;#10 EW_VEHICLE_DETECT = 0;
     #10 NS_VEHICLE_DETECT = 0;#10 EW_VEHICLE_DETECT = 0;
    #1000 $finish;
  end

  always begin
    #1 clk = ~clk;
  end
endmodule
module Traffic_Test_2;

  // Inputs
  reg NS_VEHICLE_DETECT;
  reg EW_VEHICLE_DETECT;

  // Outputs
  wire NS_RED;
  wire NS_YELLOW;
  wire NS_GREEN;
  wire EW_RED;
  wire EW_YELLOW;
  wire EW_GREEN;

  // Clock
  reg clk;

  // Counters
  wire[4:0] count1;
  wire[3:0] count2;
  wire[1:0] count3;

  // Counter Modules
  nsCounter clock1(clk, count1); 	 // Count a total of 32 seconds
  ewCounter clock2(clk, count2); 	 // Counts a total of 16 seconds
  yellowCounter clock3(clk, count3); // Counts a total of 4 seconds

  // Main Traffic Module
  Traffic CORE (count1, count2, count3, NS_VEHICLE_DETECT, EW_VEHICLE_DETECT, NS_RED, NS_YELLOW, NS_GREEN, EW_RED, EW_YELLOW, EW_GREEN);

  initial begin

    clk = 0;
    NS_VEHICLE_DETECT = 0;
    EW_VEHICLE_DETECT = 0;

    $display("  NS | EW ");
    $display("R Y G R Y G ");
    $monitor("%h %h %h %h %h %h", NS_RED, NS_YELLOW, NS_GREEN, EW_RED, EW_YELLOW, EW_GREEN);

    #1000 $finish;
  end

  always begin
    #1 clk = ~clk;
  end
endmodule

</details>
<h2>References  : </h2>
<details>
<summary>Detail</summary>
 <h3>
  1.https://electronics.stackexchange.com/questions/50890/how-do-i-implement-a-simple-finite-state-machine-with-2-t-flip-flops
 </h3>
 <h3>
 2.	https://www.electronics-tutorial.net/finite-state-machines/FSM-Applications/Traffic-Light-Controller/
 </h3>
 <h3>
 3.	https://ocw.mit.edu/courses/6-111-introductory-digital-systems-laboratory-fall-2002/09bd41368db0c3f65396b13cee7cf8fb_lab2.pdf
 </h3>
</details>

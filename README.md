 # It's a traffic light controller used at an intersection of a busy road and village road
<h1>Mini Project Design</h1>
<h2>Traffic Light Controller(  intersection of a busy road and a street road).</h2>
<h4><b>Team Members :</b> </h4>
<p>1.221CS110 - A. Yoga Anil Kumar - Anumola Yoga AnilKumar.221cs110@nitk.edu.in - 7013014805 </p>
<p>2.221CS161 - Umang Agarwal      - umangagarwal.221cs161@nitk.edu.in           -9958794560 </p>
<p>3.221CS162 - V.Taraka Ravindra  - tarakaravindra.221cs162@nitk.edu.in        - 7569248124 </p>
<h3>Abstract : </h3>
<p>
  The simple traffic light controller design project was introduced to alleviate this shortcoming and gain experience in solving implementation and interfacing problems of a modern digital system. we implement a fully functional traffic signal controller for a four-way intersection between a busy road and village road, where less traffic is present. Intersection is complete with sensors to detect the presence of vehicles waiting at or approaching the inter-section .</p>
  <p>These include HDL for modeling and finite state machines, and serial communication. Traffic lights, also known as traffic lamps, traffic signals, stoplight, stop-and-go lights semaphore or robots, are signaling devices positioned at pedestrian crossings, road intersections, and other locations to control competing flows of traffic. Traffic lights have installed in most cities around the world to control the flow of traffic.It assign the right of way to road users by the use of lights in standard colors (Red - Yellow - Green), using a universal color code (and a precise sequence, for color blind). It requires us to develop a state machine based controller for traffic signals at a four-way 
</p>
<img width="428" alt="image" src="https://github.com/Ravindra162/Traffic-Light-Controller-using-logisim-and-verilog/assets/121024571/ad6b1e87-56c2-4750-878d-f4b00c96349c">
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
 By integrating these specific timer intervals, your FSM-based traffic control system will effectively balance the needs of the highway and the street road, enhance safety, and reduce congestion, ultimately contributing to a more efficient and secure traffic management solution.
</p>
<h3>Working : </h3>
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
A = S1’ S0 T + S1 S0’ + S1 T’                   B = S0’ T + S0 T’ = S0 ^  T
Each state implies to 6 outputs such as Red light in North-south road (Busy road) as Rns
                                                                       Yellow light in North-South road as Yns
                                                                        Green light in North-South road as Gns
                                                                        Red light in East-West road (street road) as Rew
                                                                       Yellow light in East-West road as Yns
                                                                        Green light in East-West road as Gns

</p>

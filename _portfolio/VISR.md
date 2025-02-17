---
title: "Vascular Interventional Surgical Robot"
excerpt: "Short description of portfolio item number 3<br/><img src='/images/structure.pdf'>"
collection: portfolio   
---

I have designed an isomorphic master-salve Vascular Interventional Surgical Robot (VISR) for precise force measurement and navigation of endovascular tools viz. catheters and guidewires, as shown in Fig.\ref{VISR}-\ref{architecture1}. The master console aids operators in issuing manipulation commands and logs feedback from the force, rotation, and translation data. The slave manipulator uses the commands received from the master platform for actual tool navigation. Some force sensors are mounted at clamping device of the robot manipulator, so I utilized an Artificial Neural Network (ANN) for guidewire resistance force modulation with 50 mN precision. The developed ANN is a multilayer perceptron with five hidden layers and 77 neurons. The network is used to estimate distal force of guidewire from the force measured from force sensor in robot manipulator. 

<br/><img src='/images/VISR.png'>
<center>Vascular interventional surgical robot designed in SIAT, Chinese Academy of Sciences; (A) Master console; (B) Slave manipulator; (C) Surgeons teleoperate the master console in the room without being exposed to X-rays; (D) Slave manipulator placed next to pig in DSA room.</center>
<br/> 

<br/><img src='/images/control_flow.png'>
<center>Control flow of the VISR. Surgeons teleoperate the doctor’s terminal in the room without X-rays, and the slave manipulator with a robotic arm is placed beside the patient’s bed.</center>
<br/> 

<br/><img src='/images/architecture1.png'>
<center>Layers of the VISR control architecture.</center>
<br/> 

As shown in Fig.\ref{forcebox}, the robotic system includes a force box used for measuring the
tactile force that interventionalists exerted with their fingers. This force is regarded as the
interventionalists’ operative force on the guidewire or catheter in regular surgery. The force box includes a 32-prism, tiny flexible strip sensors, PCBs, and batteries. A flexible
sensor is folded and wound around the force box surface, and its data is logged as a
32-channel data multiplexed over an Analog Multiplexer (Texas Instruments). Thus, the interventionalists also operate the master device by manipulating the
flexible sensor with their finger. The force data is processed in a microcontroller STM32
 and transmitted over a Bluetooth module to the slave console in real time. The force box also reflects
information about the flexible tool’s firmness as it is held with a clamping mechanism in
the slave manipulator. The guidewire is clamped tightly when the surgeon presses hard on
the force box and vice versa.

<br/><img src='/images/forcebox.png'>
<center>The structure of the force box, which can measure the tactile force exerted by the surgeon's fingers. The force value will be used as parts of multi-modal information to optimize the control algorithm. (A) PCB layout of force box; (B) Force box includes a 32-prism,  tiny flexible strip sensors.</center>
<br/> 


To study the usage of robotic-assisted vascular interventions by surgeons and aid them in acquiring 
skills more efficiently, I designed a smart glove shown in Fig.\ref{glove}. This glove is capable of capturing and fusing information from multiple modalities, including the bending of the surgeon's fingers, the forces exerted while manipulating the vascular surgical robot, electromyographic (EMG) signals, posture angles and accelerations (IMU), as well as spatial position and orientation collected using electromagnetic sensors.

<br/><img src='/images/glove.png'>
<center>Intelligent glove for robotic catheterization skill learning.</center>
<br/> 

In addition, I utilized fuzzy PID and recurrent neural network (RNN) models such as the Long Short-Term Memory networks (LSTM) and Gated Recurrent Unit (GRU) networks to learn typical motion dynamics when running the master-slave platform. The trained network could estimate the position of the slave robot based on input motion factors. The estimated value and an appropriate compensatory value are then transferred to the slave robotic device in order to map the master platform's movements uniformly.     
The RNN models were implemented in Python and using the Keras library and the TensorFlow framework. The LSTM model contains an input layer (N$\times$3$\times$3), two hidden layer with 32 units each, and a fully connected layer that outputs a predicted value using the rectified linear unit (ReLU) activation function. The LSTM unit may extract essential features from an input sequence and store them in memory. To train the model, experimental data for various step values was stacked together, and feature scaling was applied to the data. 

<br/><img src='/images/position_prediction.png'>
<center>A stacked 2-layer architecture for robot position prediction and compensation using (a) LSTM and (b) GRU model.</center> 
<br/> 

Fig.\ref{LSTM_GRU} depicts the in-silico evaluations of the GRU and LSTM-based controllers. Although the original error increased to 40\%(2.0mm) of the input command for several phases, the minimum and greatest final errors were 0.001 mm and 0.1mm (2\% of the input command) across the steps. It depicts how the GRU-based controller may estimate the predicted slave robot response ahead of time and then use this to regress the initial position error. To validate the real-time usability of the learning-based models in the VISR, we utilized the Jetson AGX Orin development kit (NVIDIA, CA, USA) for the patient-side robot, and evaluated the model's performance under uniform and varying input commands using the control block diagram presented in Fig.\ref{control_block}. For a typical master's displacement, velocity, and the velocity ratio, the RNN model makes an appropriate prediction and checks for errors.  

<br/><img src='/images/control_block.png'>
<center>Control block with error compensation for the patient-side robot.</center> 
<br/> 

Related Pubulication: 

Chen, Xing-Yu, et al. Design and Evaluation of a Learning-based Vascular Interventional Surgery Robot. [Fibers, 10.12 (2022): 106](https://doi.org/10.3390/fib10120106)

Akinyemi, T.O., et al. Adapting Neural-Based Models for Position Error Compensation in Robotic Catheter Systems. [Applied Sciences, 12.21 (2022): 10936](https://doi.org/10.3390/app122110936)

Akinyemi, T.O., et al. Interventionalist Hand Motion Recognition with Convolutional Neural Network in Robot-assisted Coronary Interventions. [IEEE Sensors Journal](https://doi.org/10.1109/JSEN.2023.3281009)

Duan, Wenke, et al. Technical and Clinical Progress on Robot-Assisted Endovascular Interventions: A Review. [Micromachines. 14.1 (2023): 197](https://doi.org/10.3390/mi14010197)

CN Patent: A Tactile-Feedback Device and Method for Surgical Robots. [CN115137483A](https://www.researchgate.net/publication/370801433_CN_Patent_yizhongshoushujiqirendezhuduanliganzhifankuicaozongzhuangzhijifangfa)

CN Patent: A Bidirectional Guidewire Force Measurement Method for Vascular Interventional Surgical Robot. [CN114948258A](https://www.researchgate.net/publication/370801270_CN_Patent_yizhongshuangxiangdianchushijierujiqirencongduandaosilijiancezhuangzhijifangfa)




[//]: # (This is an item in your portfolio. It can be have images or nice text. If you name the file .md, it will be parsed as markdown. If you name the file .html, it will be parsed as HTML. )

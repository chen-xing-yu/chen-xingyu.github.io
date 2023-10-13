---
title: "Continuum Surgical Robot"
excerpt: "Short description of portfolio item number 1<br/><img src='/images/structure.pdf'>"
collection: portfolio   
---


Continuum robot has evolved as a novel treatment modality with better features over the traditional minimally invasive surgery, such as faster, safer, and more convenient intra-body interventions without wide incisions. They are designed to navigate
anatomical pathways through single-port access, e.g. natural orifice transluminal endoscopic surgery or minimal incisions. Continuum surgical robots have a fundamentally different structure than
conventional manipulators composed of discrete rigid links connected by joints. Their
ability to take the shape of 3D curves enables these robots to perform procedures
through smaller surgical corridors than would be possible with traditional robotic
mechanisms. During the work in Shenzhen Institute of Advanced Technology, Chinese Academy of Sciences, I lead a small group of students and design two continuum robot, a vascular interventional surgical robot and a robotic bronchoscopy system.


Robotic Bronchoscopy System
======
Related Pubulication: 

Chen, Xing-Yu, et al. Design of a Teleoperated Robotic Bronchoscopy System for Peripheral Pulmonary Lesion Biopsy. [arXiv preprint arXiv:2306.09598(2023)](https://doi.org/10.13140/RG.2.2.24714.64963).

CN Patent: A sheath with continuously adjustable stiffness, its stiffness adjustment method, and surgical equipment. [CN115920200A](https://www.researchgate.net/publication/370801235_CN_Patent_yizhonggangdulianxukediaoqiaoguanjiqigangdudiaojiefangfaheshoushushebei)

CN Patent: Biopsy Forceps Storage and Delivery Device for Bronchoscope Surgical Robots. [CN115429343A](https://www.researchgate.net/publication/370801423_CN_Patent_yizhonghuojianqianshounayudisongzhuangzhiyijizhiqiguanjingshoushujiqiren)

CN Patent: \emph{\href{https://www.researchgate.net/publication/370801247_CN_Patent_yizhongjinghuxidaozhenliaojiqirenxitongjiqikongzhifangfa}{A Respiratory Diagnosis and Treatment Robot System and its Control Method.}} PCT/CN115252146.

CN Patent: \emph{\href{https://www.researchgate.net/publication/372234328_CN_Patent_yizhongzhiqiguanjingmozujiqihuojianfangfahecaiyongqideshoushujiqiren}{A bronchoscope module and its biopsy method.}}  CN116369834A.

I am currently tasked with designing an innovative teleoperated robotic bronchoscopy system and multi-modal navigation through image and electromagnetic sensors. During the procedure, the surgeon holds a tablet console to control a flexible visual bronchoscope, inserts a flexible tube into the patient's mouth, and utilizes the robot for advancements, rotations, and adjustment of the bending angle of the front end of the flexible bronchoscope. The robot also enables control of the biopsy forceps for feeding and tissue sampling. 
<br/><img src='/images/R_B_System.png'>

The system consists of a teleoperated surgical robot designed for trans-respiratory diagnosis, along with a corresponding master-slave control system. It incorporates various components, including a flexible bronchoscope, bronchial biopsy instruments, variable stiffness catheters, a magnetic navigation device, and several tablets functioning as master consoles. The surgeon operates the tablet, and the instructions are wirelessly transmitted to the embedded system controller through the TCP/IP protocol suite. Subsequently, the robot manipulates the flexible bronchoscope in response to the issued commands. Employing a multi-operator strategy, the robot is controlled through scheduling arrangement and weight distribution, which enables mentor surgeons and trainee surgeons operate surgery simultaneously. They can observe the same surgical site and share control of robotically controlled surgical instruments. This allows trainees to gain firsthand experience of the procedure while being guided by the mentor surgeon. Additionally, the mentor surgeon can switch control to selected trainees if necessary and override their control during the bronchoscopy procedure. I developed the electrical system of the entire surgical robot, and used pyqt to design the UI interface of the system, as shown in Fig.\ref{three_tools}. We have also developed a novel Variable Stiffness Catheter (VS-Catheter) composed of Low Melting Point Alloy (LMPA) to enhance the catheter's flexibility in the context of minimally invasive surgery and expand the accessible area for bronchoscopic biopsy forceps. Compared with bronchoscope, the VS-Catheter can be inserted into narrower bronchi and offers more flexible control with dynamic stiffness.  

Additionally, to integrate endoscopic video and EM tracking information, I am employing a multimodal navigation system, utilizing the open-source software 3D Slicer, shown in Fig.\ref{3dsclicer}. It offers a range of tools for importing, processing, visualizing, and analyzing medical image data. It also provides capabilities for image registration, segmentation, and fusion. Furthermore, it includes a toolbox of navigation features, image-processing algorithms, and connections to external hardware for image-guided therapy (IGT). By combining images, tracked surgical instruments, and computer display, a comprehensive navigation system is created, enabling real-time identification of the direction and position of the bronchoscope tip and reference.

Fig.\ref{Procedure} showed the surgery procedure of robot-assisted bronchoscopy. Registration involves creating a 3D map of the patient's airways, integrated through CT or MRI to provide visual map of the surgical workspace. This map is used to guide the robotic system during the procedure. Once the registration is complete, the physician will use the 3D map to plan the bronchoscopy procedure. This may involve identifying the location of suspicious areas, such as tumors or lesions, and planning the best route to reach them. After the robotic system is set up on a passive arm and calibrated, the physician remotely controls the robotic system to examine the patient's airways with virtual bronchial navigation or EM guidance  navigation system, looks for any abnormalities or suspicious areas, and performs a biopsy or other procedure to obtain a tissue sample for further testing.	

In addition, we conducted several animal biopsy experiments using the robotic bronchoscopy system, as depicted in Fig.\ref{animal}. The system was controlled by two operators using tablets with different priorities and EM sensors were attached to the pig's forebreast and the tip of the bronchoscope. We successfully performed a biopsy procedure in which small tissue was clamped and removed from the tertiary bronchus of a pig. The implementation of the VS-Catheter enabled more flexible control of the biopsy forceps within the bronchus. The stiffness of the catheter was adjusted by energizing the resistance wire, providing adaptability based on the specific requirements of the procedure. The usability and effectiveness of the designed bronchoscopy surgical robot were demonstrated. Our work has been submitted to the 2023 IEEE BioCAS conference for publication.


Vascular Interventional Surgical Robot
======


[//]: # (This is an item in your portfolio. It can be have images or nice text. If you name the file .md, it will be parsed as markdown. If you name the file .html, it will be parsed as HTML. )

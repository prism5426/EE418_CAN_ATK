# EE 418 Final Project: CAN-BUS
### Group 17: Joe Leuschen(2162382), Yijie Li (1810605) ,xx

## Implementation and Simulations

### Task I: IDS Class

#### IDS class implemented in *ids.py*

### Task II: Offset Curves (state-of-the-art IDS)

Plot 1

<img src="results\Accumulated_offset_for_state_of_the_art_IDS_N=20.png" alt="drawing" width="400"/>

### Task III: Offset Curves  (NTP-based IDS)

Plot 2

<img src="results\Accumulated_offset_for_NTP_based_IDS_N=20.png" alt="drawing" width="400"/>

Question: Compare the slopes of the curves from Tasks 2 and 3, and comment on the similarity of the
three messages in terms of estimated clock skew from the perspective of the IDS

Response: GET EXACT CLOCK SKEWS FROM DATA I EYEBALLED

The slopes of the 0x184 and 0x180 curves in Task 2 (state-of-the-art IDS) exhibit a consistent positivity, with the 0x184 being slightly larger. Both curves consistently maintain a positive trend without observable changes in slope. In contrast, the 0x3d1 curve experiences jaggedness in clock skew around every 1500 second but also has a positive slope. It is also noting there is a steep inconsistent change of slope at t = 3100.
In terms of clock skew of the messages 0x184 and 0x180 have a consistent positive clock skew of 58 us/sec and 54 us/sec respectively. The 0x3d1 has an overall average skew of 46 us/sec although this is not consistent over the entire graph.
In Task 3, all slopes are negative, with the 0x184 and 0x180 exhibiting similar magnitudes. The 0x3d1 slope displays periodic jaggedness approximately every 1500 seconds this is similar to the Task 2 0x3d1 slope althought negative and less defined as the slope is smaller. In terms of clock skew 0x184 and 0x180 have estimated skews of -17 us/sec and -20 us/sec respectively. 
The 0x3d1 message has an average clock skew of .66 us/sec. The biggest differences between the tasks slopes is the direction of the slopes and the magnitude slope (skew) in the 0x3d1 messages. All of the Task 2 messages exhibit relatively similar positive slopes (skews) with 3x0d1 having an aspect of jaggedness while only the 0x184 and 0x180 messages of task 3 have similar large negative slopes. The 3x0d1 messsage in task 3 has a slope of less than 
1 in magnitude. It does however have a jaggedness consistent to that of message 0x3d1 in task 2 although of smaller magnitude. 


### Task IV: Offset Curves (N=30)

Plot 3

<img src="results\Accumulated_offset_for_state_of_the_art_IDS_N=30.png" alt="drawing" width="400"/>

Plot 4

<img src="results\Accumulated_offset_for_NTP_based_IDS_N=30.png" alt="drawing" width="400"/>

Question: Comparing the four figures from Tasks 2 through 3, comment on the consistency of clock skew
estimation (i.e., the slope of the curve for the same message should be the same regardless
of N ) for the state-of-the-art and the NTP-based IDSs

Response: The consistency of clock skew estimation seems to be improved as the overall slopes are the same but the lines are smoother. This is especially evident in the 0x3d1 messages as while their periodic jaggedness 
is still present there is no longer the abnormaility at t = 3100 in the state-of-the art IDS and the overall smoothness of the NTP IDS is improved. the jaggedness every 1500 seconds is not changed. 

### Task V: Masquerade Attack

Plot 5

<img src="results\Control_limits_for_state_of_the_art_IDS_during_masquerade_attack_N=20.png" alt="drawing" width="400"/>

Plot 6

<img src="results\Control_limits_for_NTP_based_IDS_during_masquerade_attack_N=20.png" alt="drawing" width="400"/>

Question: Which IDS can detect the masquerade attack? Why?

Response: 

### Task 6: Cloaking Attack

Plot 7

<img src="results\Control_limits_for_state_of_the_art_IDS_during_cloaking_attack_N=20.png" alt="drawing" width="400"/>

Plot 8

<img src="results\Control_limits_for_NTP_based_IDS_during_cloaking_attack_N=20.png" alt="drawing" width="400"/>

Question: Which IDS can detect the cloaking attack? Why?

Response: 

Question: Comparing masquerade and cloaking attacks, comment on the limitations of a clock-skew
based IDS

Response: 

## Additional Questions

### 1

Question: Briefly explain how the adversary chooses ∆T for the cloaking attack on the clock skew detector.

Response: The adversary chooses ∆T for the cloaking attack on the clock skew detector based on the estimated clock skew of the legitimate ECU which the adversary aims to impersonate. This is done in order to fool the Intrusion Detection System (IDS) which relies on clock skew as a signature for different ECUs. By manipulating its clock skew by adding a small time delay ∆T into the message inter-departure time, the adversary can mimic the clock skew of the targeted ECU, making it difficult for the IDS to detect the masquerade attack.


### 2

Question: What is Maximum Slackness Index (MSI), and what does it measure? 
briefly comment on the performance of cloaking attack on an IDS in terms of MSI.

Response: 

### 3 

Question: Based on [2], explain under what circumstances, two messages are likely to be highly correlated.
Based on the analysis in Section IV-C and Fig. 10 in [3], explain under what circumstances, two
messages are likely to be highly correlated.

Response: 

### 4

Question: Based on [3], describe how to launch the cloaking attack on the correlation detector, and briefly
explain why it works.

Response: 

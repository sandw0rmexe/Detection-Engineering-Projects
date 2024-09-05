# Detection-Engineering-Projects

## Objective
The primary objective of this project is to develop a comprehensive solution for identifying and detecting Mimikatz activity within a Windows environment. This involves creating advanced detection rules tailored to recognize Mimikatz's behavior, ensuring effective monitoring and response capabilities against this specific threat.



### Skills Learned

-Threat Detection Engineering: Developed skills in creating and refining detection rules specific to advanced threats like Mimikatz within Windows environments.

-PowerShell Scripting Analysis: Enhanced ability to analyze and interpret PowerShell scripts to identify malicious patterns indicative of credential theft tools.

-Security Event Analysis: Gained expertise in leveraging security logs to detect anomalous activities and potential security breaches.

-Adversary Emulation: Applied adversary tactics, techniques, and procedures (TTPs) using emulation tools like Atomic Red Team to test and validate detection rules.

-SIEM Integration and Rule Development: Acquired proficiency in integrating detection rules within SIEM platforms (e.g., Elastic SIEM) for real-time threat monitoring.


### Tools Used

- Security Information and Event Management (SIEM) system for log ingestion and analysis.(Elastic)
- Windows VM
- Telemetry generation tools to create realistic network traffic and attack scenarios.
- Red Canary's Atomic Red for Adversary Emulation 

## Steps
After setting up the Elastic SIEM and adding the Windows agent, the first objective was installing the Red Canary's atomic red team and start the initial attack simulation.

![image](https://github.com/user-attachments/assets/22c660c6-772b-4f77-94e7-f9dfb36e8f0f)

After initializing the attack on the Windows agent, we navigate back to the Elastic SIEM's Security section and observe to see if any alerts have triggered. As you can see there have been no alerts triggered.

![image](https://github.com/user-attachments/assets/bc087a3b-fd44-483b-91e3-45fb88e3e2dc)

After observing that there were no alerts being triggered from executing the attack, we create a rule based on the logs generated from the SIEM to confirm that an attack was indeed happening. Here's a look at the actual logs! (Specifically the Powershell logs.)

![image](https://github.com/user-attachments/assets/069c2a36-496c-48a8-803c-86a9397887c0)

After developing our detection rule we decide that we want to test the efficacy of the rule by running the EXACT same attack simulation as before on the windows host to test the efficacy of the rule we just made. We navigate to the alerts tab in the security section and these are the results.

![image](https://github.com/user-attachments/assets/93f873e8-dd8d-4a9b-8613-9265f4e97059)

Finally we perform further analysis by clicking on the rule and we see the detection and parameters that we've just devloped for the attack simulation. Just like that we've detected Mimikatz on our host environment.

![image](https://github.com/user-attachments/assets/086f54fa-5fda-4073-9261-5ec5181274c0)

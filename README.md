# Theophany Bandure - Profile

A semantic HTML5 profile and mini-portfolio page for CIS2103 Web Technologies.

## PROMPT LOG

**1. Exact Prompt:**
"Act as a professional copywriter. I am a 2nd year Software Engineering & CIS student at Africa University. I need a short, engaging bio for the 'About Me' section of my portfolio. My goal is to sound passionate about AI and web technologies while keeping it professional. Please format it as a single paragraph of 2-3 sentences."

**2. AI's Raw Output:**
"Hello there! I'm a dedicated second-year Software Engineering and CIS student at Africa University with a profound passion for Artificial Intelligence and web technologies. I am driven by the desire to craft innovative, user-centric digital solutions that bridge the gap between complex algorithms and intuitive design. Always eager to learn, I am on a mission to leverage cutting-edge technology to solve real-world challenges."

**3. Final Edited Version:**
"Hello! I am a passionate computing student at Africa University, deeply curious about the intersection of artificial intelligence and software engineering. My goal is to build accessible, user-centric web applications that solve real-world problems."

**4. Reflection:**
I changed the AI's output because the original felt a bit too verbose and used generic buzzwords ("profound passion", "bridge the gap"). I shortened it to make it sound more like my authentic voice, focusing clearly on my core interests and my practical goal of building accessible applications.

## Accessibility Review & Fix

**Issue Found During Thursday's Peer Review:** 
The peer reviewer noticed that the profile picture in the `About Me` section lacked descriptive alternative text (`alt=""`). This meant screen readers would skip the image entirely, missing out on important context about the profile owner.

**Fix Applied:**
I updated the `<img>` tag to include a meaningful description: `alt="A professional headshot of Theophany Bandure smiling"`. This ensures the image serves its purpose for all users.
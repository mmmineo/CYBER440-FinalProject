
Provide a 1-slide BLUF perspective with your understanding of what has happened. Identify the structured analytic method that you're using to organize the evidence you've found. Remember to keep it at a high level, sufficient for the CEO of your client, but don't "dumb it down."

For as much as you have figured out so far, provide a section-by-section analysis - provide the data (at a high level) that supports your analysis. You may use backup slides for the details.

### Network Data ###
- Is your network data contiguous? If not, what does your network data cover?
- Does your network data cover all systems? If not, identify where in the network that you think the capture covers and what it doesn't cover.
- Do the services that are hosted on the systems make sense for the services that should be offered from those systems.

### Forensic Image Analysis ###
- What are those systems used for?
- What user accounts exist on each system?
- What do you know about the activities or actions of the user accounts prior to the incident?
- Are there any issues with the accounts that you have found? Are they all authorized? Do you know anything about their passwords?
- What software is installed on each system? Was there anything installed recently?
- Identify and explore common vectors of attack - phishing, malicious web pages, malicious software installations, etc.

### Memory Forensics ###
- Is each of the programs running on the system a normal process?
- Are any of the processes running abnormal?
- How much memory does each process take up? Is that a normal amount?
- What do you know about the code that is running?
- Consider spinning up similar systems to do a process-by-process comparison

### Log Files ###
- For each type of log entry - what systems contribute log entries?
- For each type of log entry - are these loge entries "normal" behavior?
- Are there any time gaps in your log files?
- Are there any unusual log entries? If so, what makes them unusual?

### IOCs ###
- Identify any initial findings
- Identify any preliminary IOCs that you have found.  Provide some statement of confidence of your analysis of those IOCs.

### Questions and Concerns ###
- Identify any questions you have for the client
- Identify any concerns or issues that your team has

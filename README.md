# POUD-PersistenceTask
Experiment Files and documentation for Bhanji, J. P., Delgado, M. R., &amp; Ray, S. (2021). https://doi.org/10.1080/00952990.2021.1888960  

- PathTask-eprime folder contains e-prime files to run the behavioral task  
- code folder contains jupyter notebooks with python code to extract behavioral data from e-prime output files (description in notebook comments)  

### Task Description  
- reported in Bhanji, Delgado, Ray. (2021). https://doi.org/10.1080/00952990.2021.1888960  
- see also [Bhanji, J. P., Kim, E. S., & Delgado, M. R. (2016). Perceived control alters the effect of acute stress on persistence. Journal of Experimental Psychology: General, 145(3), 356–365.](https://doi.org/10.1037/xge0000137). [Supplement](http://supp.apa.org/psycarticles/supplemental/xge0000137/xge0000137_supp.html)     
- see also Bhanji, J. P., & Delgado, M. R. (2014). Perceived control influences neural responses to setbacks and promotes persistence. Neuron, 83(6), 1369-1375. https://doi.org/10.1016/j.neuron.2014.08.012  

#### Important Filenames (in the PathTask-eprime folder):  

- PathTask_Instruct_UncCon.es2: e-prime file for instructions and practice
rounds 
-PathTaskfmri_order1.es2, PathTaskfmri_order2.es2: Main experiment files (round order shuffled for order2)  
- images - folder of images needed for the e-prime presentation  

#### File Descriptions:  

- PathTask_Instruct_UncCon.es2: Eprime 2.0 file – Instructions & practice to go with 
main experiment file.
- PathTaskfmri_order(1|2).es2 
Experimental Design: 2 conditions within subjects (Condition changes from round to round, but not within)
Conditions: Uncontrollable Obstacles, Controllable Obstacles, Progress Events - participant receives same pattern of
obstacle setbacks in both conditions.
- Uncontrollable Obstacles - setbacks framed as random
- Controllable Obstacles - setbacks framed as due to “incorrect” response
- Progress Cues (green triangle)
Timing Information:
Event Timing - Path Choice (2s), fixation (2s/4s/6s) (50%/25%/25%), Obtacle Cue (2s), 2s/4s/6s (50%/25%/25%) Fixation (no fixation between cue and
outcome for Progress Cues), Obstacle Outcome-Setback received/avoided (2s), fixation (2s/4s/6s) (50%/25%/25%)  

Trial Counts and other details:  
10 rounds, 32 obstacle cues, 20 setbacks and 12 avoided setbacks (60% of obstacles result in setback), 20
persistence choices (after each setback), 12 progress cues  

How to interpret output files:  
EventType: 1=uncontrollable obstacle, 2=controllable obstacle, 3=progress cue, 4=path choice, 6=goal feedback  

Lose: 1=setback received, 0=setback avoided, -1=event was path choice or goal feedback  

Persist: 1 = choice to try again on the same path where a setback was just experienced, 0 = choice to switch to a
different path than the one where the setback was experienced, -2=first path choice of the round, not included in
persistence calculation, -1 = no response given for path choice  

Other notes:  

To calculate Behavioral Persistence for each participant,  take the number of Persist choices (coded as “1” in the
“Persist” column of output for each condition, and divide by the total number of post-setback choices (choices with
a “1” or “0” in the Persist column. Missed choices have a “-2” in the “Persist” column).  
The “Switch” column in the output has value “1” when the participant chooses a path that is lower in value than the
current path, “0” if they choose the same path or a higher value path.  
If a participant does not change their response after a controllable setback (i.e., fails to learn from a mistake), then a
setback is received and the study continues on.  

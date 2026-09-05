# Activity 4: ReelWave Recommendation Meltdown
## Sessions 7, 8, 9
## Due date: 09/13/2026
## Adriana Rosales (ID: 00446182) 

---

# Activity Description

## The Case

ReelWave, a streaming platform, woke up to a wave of complaints: kids' profiles are getting horror-movie recommendations, and horror fans are getting cooking shows.
You've been hired as an **AI Detective** to find out where in ReelWave's AI pipeline the fault lives — is it bad **Data**, bad **Information**, or bad **Knowledge**?

This activity is a single interactive app — no coding required, but you will make a few precise, guided edits and observe what changes. Everyone in the class uses the **same shared link** (your instructor will post it), so there's nothing to install.

**App link:** https://esgbtzjappjhcnqvn9s5jbm.streamlit.app/

If you'd rather run it on your own machine instead of using the shared link, see **Running It Yourself** below.

### The App

The app has four tabs, each mapping to one of this unit's sessions:

1. **Data (Session 7)** — Raw, unprocessed interaction logs. 
Use the filters to explore, then click "Show data quality report" to see how much of the data is corrupted (duplicates, missing values).
2. **Information (Session 7)** — The same data, cleaned and aggregated into per-genre averages. 
Switch the profile type and look for anything that seems out of place.
3. **Knowledge Graph (Session 8)** — The actual knowledge the recommendation engine relies on: a network of content, genres, and age groups connected by relationships. 
One relationship in this graph is wrong, and it's the real root cause of the meltdown.
4. **Interrogation Room (Session 9)** — A small fact/rule/query engine (in the spirit of Prolog) that reasons about who or what caused the bug. 
Run a query, then add one new fact and run it again.

##
# Your Tasks

1. **Investigate the Data tab.** Take a screenshot of the data quality report.
   💡 *Hint:* "Corrupted" rows are either exact duplicates (the same log entry logged twice) or rows missing a rating. You don't need to count anything by hand — just click "Show data quality report."

<img width="614" height="562" alt="Information_Suspicious" src="https://github.com/user-attachments/assets/43ce2430-e2c7-4b47-9682-74d066a67cd6" />
<img width="618" height="566" alt="Data_Report" src="https://github.com/user-attachments/assets/fb5de57d-8f9e-4aa3-b2a6-099ed0f67db3" />


##
2. **Investigate the Information tab.** Find the profile type + genre combination with a suspiciously high match score. Take a screenshot.
   💡 *Hint:* Switch the dropdown between kids / teen / adult and compare the bars. Ask yourself: does it make sense for a *kids* profile to score high on any particular genre? One bar shouldn't be there at all.

![Uploading Information_Suspicious.png…]()


##
3. **Investigate the Knowledge Graph tab.** Identify the one `similar_to` edge that doesn't belong. Take a screenshot of the "Top 3 Recommended" list *before* you touch anything.
   💡 *Hint:* Node colors tell you what kind of thing each node is (blue = content, orange = genre, green = age group). Find the "Bunny Buddies" node and look at every line coming out of it — one of them connects it to something clearly not made for kids.

<img width="1182" height="551" alt="KnowledgeGraph_Before" src="https://github.com/user-attachments/assets/3ed18dd8-ce89-4c3b-a272-985e8fd2e122" />


##
4. **Fix it.** Use the "Fix an Edge" control to remove that one bad edge. Take a screenshot of the "Top 3 Recommended" list *after* the fix.
   💡 *Hint:* The dropdown under "Fix an Edge" lists every `similar_to` edge by name — just pick the one you spotted in Step 3.

<img width="1205" height="575" alt="KnowledgeGraph_After" src="https://github.com/user-attachments/assets/92f32ecd-4f3d-443c-b599-359462bc188d" />


##
5. **Investigate the Interrogation Room.** Run a query against each suspect. Take a screenshot of the reasoning trace and verdict for the suspect you believe is responsible.
   💡 *Hint:* Query all four suspects, not just one — seeing a GUILTY trace next to a NOT GUILTY trace makes it much easier to see what the rule is actually checking. Pay attention to two things in each trace: did the suspect have access, and did their edit happen "overnight"?

**INTERROGATION BEFORE**
<img width="633" height="607" alt="Interrogation_Before_01" src="https://github.com/user-attachments/assets/5116533b-d5d6-41e4-92e7-49c02a71773d" />

<img width="629" height="578" alt="Interrogation_Before_02" src="https://github.com/user-attachments/assets/51a6dab9-5668-4c53-9d26-f43f883716dd" />

<img width="626" height="603" alt="Interrogation_Before_03" src="https://github.com/user-attachments/assets/ecb7fa71-1f48-4e93-a116-7d01fd051d86" />

<img width="637" height="571" alt="Interrogation_Before_04" src="https://github.com/user-attachments/assets/5998f5c2-7c63-44d9-8122-5df69ccd4b89" />



##
6. **Add one new fact.** Use the "Add a New Fact" form to give the engine one additional piece of evidence, then re-run a query and see whether the verdict changes. Take a screenshot of the new result.
   💡 *Hint:* The engine only cares about the hour of the time you type in. Pick a suspect who came back NOT GUILTY, give them a new edit time somewhere between 00:00 and 05:59, and re-run the query.

 **INTERROGATION AFTER**  

<img width="625" height="650" alt="Interrogation_After" src="https://github.com/user-attachments/assets/6d438cf7-dcb5-478c-a58f-120815f7d89f" />


##
7. **Write your report.** 

**Q1.** What did you learn about the difference between data, information, and knowledge?

- Data is raw and unprocessed. Information is cleaned and organized data. Knowledge is structured relationships that allow reasoning. The ReelWave case showed how each layer can fail differently — bad data leads to wrong information, and bad knowledge leads to wrong recommendations.

**Q2.** How did fixing the knowledge graph edge affect recommendations?

- Removing the wrong edge between “Bunny Buddies” and horror movies corrected the system’s logic. After the fix, the recommendations became appropriate for kids, proving how crucial accurate semantic relationships are.

**Q3.** What role did logic programming play in identifying the culprit? 

- Logic programming allowed the system to reason based on facts and rules. By adding a new fact (overnight edit time), the verdict changed, showing how logical inference updates conclusions when new evidence appears.

**Q4.** How does this activity connect to semantic networks and AI concepts?  

- It demonstrated how semantic networks organize knowledge and how logic programming uses that structure to reason. Together, they form the foundation of intelligent systems capable of understanding and correcting errors.

**Q5.** What personal insight did you gain from this investigation?  

- I realized that AI systems depend on clean data, accurate information, and well‑structured knowledge. Even a small mistake in relationships can cause major consequences, so attention to detail and reasoning are essential in AI design.

##


# References:
- [Streamlit documentation](https://docs.streamlit.io/)
- [Markdown Guide](https://www.markdownguide.org/basic-syntax/)

#ELECTION ANALYSIS
Create an Election Analysis using Python

##Overviewof Election Audit
###You have been asked to help an Election Committee to run further analysis to complete an audit from the results provided form the most recent election. The ask is to:
•	Determine the total number of votes
•	List the names of candidates who received votes
•	Display the total number for votes for each candidate
•	Display the percentage of votes each candidate received
•	Display the winner based on the winning number of votes

##Election-Audit Results
•	How many votes were cast in this congressional election?
    https://github.com/abegjura/Election_Analysis/blob/main/Resources/Total_Votes.PNG
 
      # Initialize a total vote counter.
      total_votes = 0

•	Provide a breakdown of the number of votes and the percentage of total votes for each county.
    https://github.com/abegjura/Election_Analysis/blob/main/Resources/County_Votes.png
 
# 6a: Write a repetition statement to get the county from the county dictionary.
    for county_name in county_votes:
        # 6b: Retrieve the county vote count.
        county = county_votes.get(county_name)

        # 6c: Calculate the percent of total votes for the county.
        county_percentage = float(county) / float(total_votes) * 100
        county_results = (
            f"{county_name}: {county_percentage:.1f}% ({county:,})\n")

         # 6d: Print the county results to the terminal.
        print(county_results, end="")
         # 6e: Save the county votes to a text file.
        txt_file.write(county_results)
         # 6f: Write a decision statement to determine the winning county and get its vote count.
        if (county > winning_county) and (county_percentage > winning_c_percentage):
            winning_county = county
            winning_c_candidate = county_name
            winning_c_percentage = county_percentage

    # 7: Print the county with the largest turnout to the terminal.
    winning_county_summary = (
        f"\n-------------------------\n"
        f"Largest County Turnout: {winning_c_candidate}\n"
        f"Winning County Vote: {winning_county:,}\n"
        f"Winning County Percentage: {winning_c_percentage:.1f}%\n"
        f"-------------------------\n\n"
        f"Candidate Percentage of Votes:\n"
        f"-------------------------\n")
    print(winning_county_summary)


•	Which county had the largest number of votes?
    https://github.com/abegjura/Election_Analysis/blob/main/Resources/Largest_num_votes.png
 


•	Provide a breakdown of the number of votes and the percentage of the total votes each candidate received
     https://github.com/abegjura/Election_Analysis/blob/main/Resources/Candidate_percentage.png   
 
 # Save the final candidate vote count to the text file.
    for candidate_name in candidate_votes:

        # Retrieve vote count and percentage
        votes = candidate_votes.get(candidate_name)
        vote_percentage = float(votes) / float(total_votes) * 100
        candidate_results = (
            f"{candidate_name}: {vote_percentage:.1f}% ({votes:,})\n")

        # Print each candidate's voter count and percentage to the
        # terminal.
        print(candidate_results)
        #  Save the candidate results to our text file.
        txt_file.write(candidate_results)

•	Which candidate won the election, what was their vote count, and what was their percentage of the total votes?
    https://github.com/abegjura/Election_Analysis/blob/main/Resources/Winner.png
 
# Determine winning vote count, winning percentage, and candidate.
        if (votes > winning_count) and (vote_percentage > winning_percentage):
            winning_count = votes
            winning_candidate = candidate_name
            winning_percentage = vote_percentage

    # Print the winning candidate (to terminal)
    winning_candidate_summary = (
        f"\n-------------------------\n"
        f"Winner: {winning_candidate}\n"
        f"Winning Vote Count: {winning_count:,}\n"
        f"Winning Percentage: {winning_percentage:.1f}%\n"
        f"-------------------------\n")
    print(winning_candidate_summary)

    # Save the winning candidate's name to the text file
    txt_file.write(winning_candidate_summary)


## Election-Audit Summary
Our most recent audit has shown we can use powerful data engineering tools to run through a large amount of results and provide required information in a timely manner. Although the current analysis was used for the most recent congressional election in three counties, we can expand the analysis to be state-wide if we can utilize the source information for all counties. This will allow Election Auditors to have state-wide results available in a very short amount of time.

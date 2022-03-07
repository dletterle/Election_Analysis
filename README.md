# Election_Analysis
Analysis of election results utilizing command prompt, python, git-bash, and visual studio code

**Devliverable 1**

#pre-work

import csv
import os
file_to_load = os.path.join("Resources/election_results.csv")
file_to_save = os.path.join("analysis", "election_analysis.txt")

#Step 1

total_votes = 0
candidate_options = []
county_options = []
candidate_votes = {}
county_votes = {}

#Step 2

winning_candidate = ""
winning_count = 0
winning_percentage = 0

#Step 3

with open(file_to_load) as (election_data)
  reader = csv.reader(election_data)
header = next(reader)
for row in reader:
  total_votes = total_votes + 1
  candidate_name = row[2]
  county_name = row[1]
  
  if candidate_name not in candidate_options:
    candidate_options.append(candidate_name)
    candidate_votes[candidate_name] = 0
  
  candidate_votes[candidate_name]+=1
  
#Step 4
if county_name not in county_list:
  county_list.append(county_name)
  county_votes[county_name] = 0
  
#Step 5
county_votes[county_name]+=1

#Step 6
for county_name in county_votes:
  county_vote_count = county_votes[county_name]
  county_vote_percentage = float(county_vote_count) / float(total_votes) * 100
  
  county_results = (f"{county_name}: {county_vote_percentage:.1f}% ({county_vote_count:,})")
  print(county_results)
  
  txt_file.write(county_results +"\n")
  
  if (county_vote_count > largest_county_turnout) and (county_vote_percentage > largest_county_percentage):
    largest_county_turnout = county_vote_count
    largest_county_percentage = county_vote_percentage
    largest_county = county_name
    
#Step 7
  winning_county_summary = (
     f"\n-------------------------\n"
     f"Largest County Turnout: {largest_county}\n"
     f"-------------------------\n")
  print(winning_county_summary)
  
**Deliverable 2****

#Step 8
txt_file.write(winning_county_summary)

for candidate_name in candidate_votes:
    votes = candidate_votes.get(candidate_name)
    votes_percentage = float(votes) / float(total_votes) * 100
    candidate_results = (
      f"{candidate_name}: {vote_percentage:.1f}% ({votes:,})\n")
  print(candidate_results) 
  txt.file.write(candidate_results)
  
  if (votes > winning_count) and (vote_percentage > winning_percentage):
    winning_count = votes
    winning_candidate = candidate_name
    winning_percentage = vote_percentage
    
   winning_candidate_summary = (
        f"-------------------------\n"
        f"Winner: {winning_candidate}\n"
        f"Winning Vote Count: {winning_count:,}\n"
        f"Winning Percentage: {winning_percentage:.1f}%\n"
        f"-------------------------\n")
    print(winning_candidate_summary)    
    
txt_file.write(winning_candidate_summary)
    
**Deliverable 3****

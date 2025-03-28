ChatGPT Prompts use to create the Toy Dataset

\*There is a lot of flexibility when generating the toy dataset with
ChatGPT, but it\'s important to be specific in your prompts to get the
desired results. The highlighted portions can be changed in order to
create a larger or smaller toy dataset.

Link to example session:

<https://chatgpt.com/share/67d927eb-c6ac-8002-a75a-31ba16bf6cf5>

[Creating the 25 fake students in the StudentDemographics
sheet]{.underline}

Prompt: "Can you generate a COPY-ABLE Excel-compatible dataset of 5 fake
students with columns for StudentID, StudentFirstName, StudentLastName,
Race/Ethnicity, GenderAssignedAtBirth, GenderIdentity, Address, City
(either Springfield, Decatur, or Peoria), State (IL), ZipCode, Birthdate
(format MM/DD/YYYY), NumOfSiblings, SES (High/Middle/Low),
StableLivingSituation (should be a range 1-5), and FoodInsecure (should
be a range 1-5)? The data should be randomized but realistic. I want to
be able to just copy and paste your output straight into an Excel
sheet."

\*Note: Since we needed real Illinois addresses, we manually inputted
the address and zip code after searching on Zillow.

[Creating the IndividualSchoolTrajectory Data]{.underline}

Prompt: "Generate a tab-separated values (TSV) table for Excel with the
following columns: StudentID (should correspond to the fake student ID),
ExpectedGraduationDate (year only), CourseofStudy, GPA (on a 4.0 scale),
GradeDistribution(A-F), PhysicalDisabilityStatus, Neurodiverse/Learning
Disability, IEP(Y/N). The data should include 5 unique students with a
variety of courses, GPAs, and grade distributions. Ensure disabilities
and neurodivergent conditions are varied across the students. The table
should be structured so that it can be copied directly into Excel
without modifications. Some students should have multiple physical
disabilities. There should also be some students with multiple
neurodivergent conditions."

[Generating SchoolDemographics data]{.underline}

Prompt: "Generate a tab-separated values (TSV) dataset for Excel with
the following columns: TotalSchoolDays, SchoolSize,
Student:TeacherRatio, YearOpened, Four-YearGraduationRate(Overall \| By
Race/Gender), Five-YearGraduationRate(Overall \| By Race/Gender),
RankedInDistrict, RankedInState, ACTAverage, SATAverage. The dataset
should include six unique schools with varied sizes, student-teacher
ratios, graduation rates, and rankings. The data should be formatted so
that it can be copied directly into Excel without modifications."

\*Since we needed real schools, the data for SchoolID, SchoolAddress,
City, State, ZipCode, SchoolDistrict, SchoolType, EducationLevel, and
SchoolName was manually added. This information was sourced directly
from each school\'s website

[Generating StudentSchoolPresence data]{.underline}

Prompt: "Generate a tab-separated values (TSV) dataset for Excel with
the following columns: StudentID, SchoolID, DaysPresent,
ExcusedAbsences, UnexcusedAbsences, Tardies, DatesAbsent (MM/DD/YYYY),
ReasonGiven (Y/ N/A, AbsenceNote, ReasonCategory(Medical, Athletics,
Family, Appointment, Mental health, Transportation). You do not need to
have N/A for each of the Reasons given if they are not applicable. You
also only need to have a \"Y\" or \"N/A\" for the ReasonGiven category
Use at least 5 students with varied attendance records. Some should have
perfect attendance (with \"N/A\" in absence-related columns), while
others should have a mix of excused/unexcused absences and tardies.
Ensure StudentID and SchoolID remain logically related across the
dataset. A StudentID should always correspond to the same SchoolID.
Ensure numeric fields (like DaysPresent) are properly formatted so Excel
recognizes them as numbers. Use semicolons (;) to separate multiple
values in DatesAbsent, ReasonGiven, AbsenceNote, and ReasonCategory.
Format AbsenceNote properly so that each absence explanation follows
this structure: \"\[Student\] \[had reason\] and \[explanation\].\"
Example: \"John had a high fever and chills, so we kept him home to
recover.\" Another example: \"Emily missed school due to transportation
issues when the car wouldn't start.\" Ensure the data pastes cleanly
into Excel without apostrophes, incorrect date formatting, or errors
requiring conversion.\"

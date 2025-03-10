# Module-8-Input-Output-string-manipulation-and-plyr-package
# Step 1
# Install necessary packages (if not installed)
install.packages("plyr")

# Load required libraries
library(plyr)

# Read dataset
Assignment_6_Dataset <- read.table(file.choose(), header = TRUE, sep = ",", stringsAsFactors = FALSE)

# Calculate mean Grade by Sex using plyr
students_gendered_mean <- Assignment_6_Dataset %>%
  group_by(Sex) %>%
  summarise(Grade.Average = mean(Grade, na.rm = TRUE))

# Write output to a file
write.table(students_gendered_mean, "Students_Gendered_Mean.txt", row.names = FALSE, sep = "\t")

# Display the result
print(students_gendered_mean)

# Step 2
# Load necessary library
library(plyr)

# Read dataset
Assignment_6_Dataset <- read.table(file.choose(), header = TRUE, sep = ",", stringsAsFactors = FALSE)

# Filter dataset for names containing the letter "i" (case-insensitive)
i_students <- subset(Assignment_6_Dataset, grepl("i", Name, ignore.case = TRUE))

# Write filtered names to a CSV file
write.csv(i_students, "Filtered_Students_Names.csv", row.names = FALSE)

# Display the filtered dataset
print(i_students)

# Step 3
# Load necessary library
library(plyr)

# Read dataset from file
Assignment_6_Dataset <- read.table(file.choose(), header = TRUE, sep = ",", stringsAsFactors = FALSE)

# Filter dataset for names containing the letter "i" (case-insensitive)
i_students <- subset(Assignment_6_Dataset, grepl("i", Name, ignore.case = TRUE))

# Save the filtered dataset as a CSV file
write.csv(i_students, file = "Filtered_Students_Names.csv", row.names = FALSE)

# Display confirmation message
cat("Filtered dataset saved as 'Filtered_Students_Names.csv'\n")

# Print the filtered dataset to confirm
print(i_students)

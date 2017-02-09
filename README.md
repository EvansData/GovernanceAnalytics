# GovernanceAnalytics
#  Use of R and Python to improve data in a public policy context

# Often, data must be uploaded into the R Studio Global Environment
install.packages("readxl")
library(readxl)
folderName='data'
fileName='cities.xlsx'  # Creates a list
fileExcel=file.path(folderName,fileName)
dataFromExcel=read_excel(fileExcel,1) # table '1'
# Load the excel file into Global Environment

class(region)

region[,c(visits2015)]

city=c(dataFromExcel$"city")
region=c(dataFromExcel$"region")
visits2015=c(dataFromExcel$visits2015)
visits2013=c(dataFromExcel$visits2013)

dataFromExcel[4]
dataFromExcel["city",] # why is it coming out as rows? 

dataFromExcel[which.max(dataFromExcel$visits2015)] # most visited city

VisitAsia=dataFromExcel[dataFromExcel$region=='Asia',] # set up the data request
VisitAsia[which.min(VisitAsia$visits2013),] # requesting least visited Asian city

tail(VisitAsia[order(-VisitAsia$visits2015),],n=3) # Three least visited Asian cities

tail(VisitAsia[order(-VisitAsia$visits2013),],n=1) # least
head(VisitAsia[order(-VisitAsia$visits2013),],n=1) # most

which.min(dataFromExcel[dataFromExcel$region %in% city$Asia])

which.min(dataFromExcel$visits2015)

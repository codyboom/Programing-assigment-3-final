#1 Method
  Best4<-function(state){  
    out1<-outcome_of_care_measures[,c(2,7,11,17,23)]
    names(out1)
    out1$`Hospital 30-Day Death (Mortality) Rates from Heart Attack`<-as.numeric(as.character(
      out1$`Hospital 30-Day Death (Mortality) Rates from Heart Attack`)) 
  
   out2<-out1[which(out1$State == state & out2$`Hospital 30-Day Death (Mortality) Rates from Heart Attack` == 
                     min(out2$`Hospital 30-Day Death (Mortality) Rates from Heart Attack`, na.rm = T)),]
  
    return(out2$`Hospital Name`)}
  Best4("TX")
  #result
    > Best4("TX")
        character(0)
         Warning message:
         In Best4("TX") : NAs introduced by coercion

#Method 2
  best5<-function(state){
   out1<-outcome_of_care_measures[,c(2,7,11,17,23)]
   names(out1)
    out1$`Hospital 30-Day Death (Mortality) Rates from Heart Attack`<-as.numeric(as.character(
      out1$`Hospital 30-Day Death (Mortality) Rates from Heart Attack`)) 
  
   out2<-out1[which(out1$State == state),]
  
    out3<-out2[which(out2$`Hospital 30-Day Death (Mortality) Rates from Heart Attack` == 
                     min(out2$`Hospital 30-Day Death (Mortality) Rates from Heart Attack`, na.rm = T)),]
   return(out3$`Hospital Name`)}
#Result
> best5("TX")
[1] "CYPRESS FAIRBANKS MEDICAL CENTER"
Warning message:
In best5("TX") : NAs introduced by coercion

A simple R script to check resident ID number from China.

```R
check_CHN_ID <- function(id) {
  ids <- strsplit(as.character(id),'')[[1]]
  if(length(ids) < 18) return(FALSE)
  s <- sum(2^(17:1) %% 11 * as.numeric(ids[1:17]))
  n <- (12 - s%%11) %% 11
  ifelse(n<10, n == as.numeric(ids[18]), toupper(ids[18]) == 'X')
}
```

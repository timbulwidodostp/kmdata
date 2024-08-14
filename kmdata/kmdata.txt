# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# A curated database of reconstructed individual patient-level data from 153 oncology clinical trials Use kmdata With (In) R Software
install.packages("remotes")
remotes::install_github("raredd/kmdata")
library("kmdata")
kmdata = read.csv("https://raw.githubusercontent.com/timbulwidodostp/kmdata/main/kmdata/kmdata.csv",sep = ";")
# Estimation A curated database of reconstructed individual patient-level data from 153 oncology clinical trials Use kmdata With (In) R Software
kmdata_1 <- survfit(Surv(time, status) ~ 1, kmdata)
kmdata_1
kmdata_2 <- summary(kmdata_1, times = 0:8 * 100)
kmdata_2
kmdata_3 <- ipd(kmdata_1$time, kmdata_1$surv, kmdata_2$time, kmdata_2$n.risk)
kmdata_4 <- survfit(Surv(time, event) ~ 1, kmdata_3)
kmdata_4
# A curated database of reconstructed individual patient-level data from 153 oncology clinical trials Use kmdata With (In) R Software
# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Finished
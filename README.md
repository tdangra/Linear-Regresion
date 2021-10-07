# Linear-Regresion
# To create the linear regression model

gamod <- lm(Population~Year, data=Georgia)
coeff = coefficients(gamod)
eq = paste0("Population = ", round(coeff[2],1), "Year", round(coef[1],1))                                                      
plot(Georgia, main=eq, xlab= "Year", ylab = "Population", cex.axis = 0.6, col=6,
     col.main=8, col.lab=4, font.axis =4,
     font.lab =4, font.main =4)
abline(gamod, col = "blue")
mean.pop = mean(Georgia$Population)
abline(h=mean.pop)

# To check for linearity

library(ggplot2)
library(scales)
scatter.smooth(Georgia$Year, Georgia$Population,
                main = "Population Vs Year", xlab = "Year",
                ylab = "Population", cex.axis = 0.60, col=6,
                col.main = 8, col.lab=4, font.axis=4,
                font.lab=4, font.main = 4)

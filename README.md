# Java Final Project (ISM3254)


-------

# Description <a name="description">

A local Apple store needs a program to automatically analyze its monthly sales. The manager would like to gain insight into how popular different categories of Apple products are in her store. She knows the total daily sales of the following four categories: Mac, iPhone, iPad, and Watch from the following sales report:

<p align="center">
Sales Report: <br/>
<img src="https://i.imgur.com/baHBcyk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

Your program’s input is five lists, such as follows. The number of values inside each list might be up to 31 values for 31 days. You can simply set the number of days as 4 [with the following dataset].<br />

int[] days = {1, 2, 3, 4};

int[] mac = {11500, 9000, 13000, 15000};

int[] iphone = {1100, 5000, 3400, 100000};

int[] ipad = {900, 4300, 1000, 200000};

int[] watch = {0, 300, 120, 500};

The manager wants your program to answer the following four questions.
1. How many days are in this period (e.g., 28, 30, 31)?
2. What are the total sales for each category of products?
3. What is the most popular product category, based on the total sales in this period?
4. Which day the store has the highest total sales over all categories?

**** Each question should be answered in a “method” with inputs and returns as follows (do not use void methods).

# My Answer  <a name="scenario">

```ruby
public class Ospina { //Nicholas Ospina
    public static int getTotalDays(int[] days) {
        return days.length;
}
    public static int getTotalSales(int[] sales) {
        int total = 0;
        for (int sale : sales) {
            total += sale;
}
        return total;
    }
    public static String getMostPopularCategory(int[] mac, int[] iphone, int[]
ipad, int[] watch) {
        int totalMac = getTotalSales(mac);
        int totaliPhone = getTotalSales(iphone);
        int totaliPad = getTotalSales(ipad);
        int totalWatch = getTotalSales(watch);
        if (totalMac > totaliPhone && totalMac > totaliPad && totalMac >
totalWatch) {
            return "Mac";
        } else if (totaliPhone > totalMac && totaliPhone > totaliPad && totaliPhone
> totalWatch) {
            return "iPhone";
        } else if (totaliPad > totalMac && totaliPad > totaliPhone && totaliPad >
totalWatch) {
            return "iPad";
        } else {
            return "Watch";
        }
}
    public static int getDayWithHighestSales(int[] days, int[] mac, int[] iphone,
int[] ipad, int[] watch) {
        int highestSales = 0;
        int highestDay = -1;
        for (int i = 0; i < days.length; i++) {
            int totalSales = mac[i] + iphone[i] + ipad[i] + watch[i];
            if (totalSales > highestSales) {
                highestSales = totalSales;
                highestDay = days[i];
            }
}
        return highestDay;
    }
    public static void main(String[] args) {
        int[] days = {1, 2, 3, 4};
        int[] mac = {11500, 9000, 13000, 15000};
        int[] iphone = {1100, 5000, 3400, 100000};
        int[] ipad = {900, 4300, 1000, 200000};
        int[] watch = {0, 300, 120, 500};
int totalDays = getTotalDays(days);

        int totalMacSales = getTotalSales(mac);
        int totaliPhoneSales = getTotalSales(iphone);
        int totaliPadSales = getTotalSales(ipad);
        int totalWatchSales = getTotalSales(watch);
        String mostPopularCategory = getMostPopularCategory(mac, iphone, ipad,
watch);
        int dayWithHighestSales = getDayWithHighestSales(days, mac, iphone, ipad,
watch);
} }
System.out.println("Total days: " + totalDays);
System.out.println("Total Mac sales: " + totalMacSales);
System.out.println("Total iPhone sales: " + totaliPhoneSales);
System.out.println("Total iPad sales: " + totaliPadSales);
System.out.println("Total Watch sales: " + totalWatchSales);
System.out.println("Most popular category: " + mostPopularCategory);
System.out.println("Day with highest sales: " + dayWithHighestSales);
```

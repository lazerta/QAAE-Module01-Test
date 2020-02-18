[TOC]



## 3.1

```mysql
SELECT *
FROM payments
WHERE customerNumber = '141'
  AND year(paymentDate) = '2004';
```
**Result**:

<!DOCTYPE html>
<html>
<head>
  <title></title>
</head>
<body>
<table border="1" style="border-collapse:collapse">
<tr><th>customerNumber</th><th>checkNumber</th><th>paymentDate</th><th>amount</th></tr>
<tr><td>141</td><td>DB583216</td><td>2004-11-01</td><td>36140.38</td></tr>
<tr><td>141</td><td>HJ32686</td><td>2004-01-30</td><td>59830.55</td></tr>
<tr><td>141</td><td>ID10962</td><td>2004-12-31</td><td>116208.40</td></tr>
<tr><td>141</td><td>MC46946</td><td>2004-07-09</td><td>35420.74</td></tr>
<tr><td>141</td><td>MF629602</td><td>2004-08-16</td><td>20009.53</td></tr>
<tr><td>141</td><td>NU627706</td><td>2004-05-17</td><td>26155.91</td></tr></table>
</body>
</html>



##  3.2

```mysql
SELECT contactFirstName,contactLastName,sum(quantityOrdered) from customers inner join orders using(customerNumber) inner join orderdetails using (orderNumber)  group by contactFirstName,contactLastName;
```

Result:

<!DOCTYPE html>
<html>
<head>
  <title></title>
</head>
<body>
<table border="1" style="border-collapse:collapse">
<tr><th>contactFirstName</th><th>contactLastName</th><th>sum(quantityOrdered)</th></tr>
<tr><td>Adrian</td><td>Huxley</td><td>1601</td></tr>
<tr><td>Akiko</td><td>Shimamura</td><td>1150</td></tr>
<tr><td>Allen</td><td>Nelson</td><td>795</td></tr>
<tr><td>Ann </td><td>Brown</td><td>937</td></tr>
<tr><td>Anna</td><td>O&#39;Hara</td><td>1469</td></tr>
<tr><td>Annette </td><td>Roulet</td><td>687</td></tr>
<tr><td>Arnold</td><td>Cruz</td><td>961</td></tr>
<tr><td>Ben</td><td>Calaghan</td><td>545</td></tr>
<tr><td>Brian</td><td>Chandler</td><td>500</td></tr>
<tr><td>Carine </td><td>Schmitt</td><td>270</td></tr>
<tr><td>Catherine </td><td>Dewey</td><td>796</td></tr>
<tr><td>Christina </td><td>Berglund</td><td>647</td></tr>
<tr><td>Dan</td><td>Lewis</td><td>666</td></tr>
<tr><td>Daniel</td><td>Da Silva</td><td>684</td></tr>
<tr><td>Daniel </td><td>Tonini</td><td>637</td></tr>
<tr><td>Dean</td><td>Cassidy</td><td>490</td></tr>
<tr><td>Diego </td><td>Freyre</td><td>9327</td></tr>
<tr><td>Dominique</td><td>Perrier</td><td>1001</td></tr>
<tr><td>Dorothy</td><td>Young</td><td>1248</td></tr>
<tr><td>Eduardo </td><td>Saavedra</td><td>882</td></tr>
<tr><td>Elizabeth</td><td>Devon</td><td>1046</td></tr>
<tr><td>Elizabeth </td><td>Lincoln</td><td>873</td></tr>
<tr><td>Eric</td><td>Natividad</td><td>1524</td></tr>
<tr><td>Francisca</td><td>Cervantes</td><td>668</td></tr>
<tr><td>Franco</td><td>Ricotti</td><td>272</td></tr>
<tr><td>Frédérique </td><td>Citeaux</td><td>779</td></tr>
<tr><td>Georg </td><td>Pipps</td><td>1442</td></tr>
<tr><td>Giovanni </td><td>Rovelli</td><td>1650</td></tr>
<tr><td>Helen </td><td>Bennett</td><td>895</td></tr>
<tr><td>Henriette </td><td>Pfalzheim</td><td>936</td></tr>
<tr><td>Jan</td><td>Klaeboe</td><td>787</td></tr>
<tr><td>Janine </td><td>Labrune</td><td>1832</td></tr>
<tr><td>Jean </td><td>Fresnière</td><td>717</td></tr>
<tr><td>Jean</td><td>King</td><td>929</td></tr>
<tr><td>Jeff</td><td>Young</td><td>1775</td></tr>
<tr><td>Jerry</td><td>Tseng</td><td>357</td></tr>
<tr><td>Jesus</td><td>Fernandez</td><td>468</td></tr>
<tr><td>Jonas </td><td>Bergulfsen</td><td>1082</td></tr>
<tr><td>José Pedro </td><td>Roel</td><td>589</td></tr>
<tr><td>Julie</td><td>Brown</td><td>1447</td></tr>
<tr><td>Julie</td><td>King</td><td>903</td></tr>
<tr><td>Julie</td><td>Murphy</td><td>692</td></tr>
<tr><td>Julie</td><td>Young</td><td>1060</td></tr>
<tr><td>Juri</td><td>Hashimoto</td><td>1179</td></tr>
<tr><td>Juri</td><td>Yoshido</td><td>1036</td></tr>
<tr><td>Jytte </td><td>Petersen</td><td>1315</td></tr>
<tr><td>Kalle</td><td>Suominen</td><td>1031</td></tr>
<tr><td>Kelvin</td><td>Leong</td><td>1111</td></tr>
<tr><td>Kwai</td><td>Lee</td><td>1631</td></tr>
<tr><td>Laurence </td><td>Lebihan</td><td>804</td></tr>
<tr><td>Leslie</td><td>Murphy</td><td>636</td></tr>
<tr><td>Leslie</td><td>Taylor</td><td>287</td></tr>
<tr><td>Maria</td><td>Hernandez</td><td>720</td></tr>
<tr><td>Marie</td><td>Bertrand</td><td>836</td></tr>
<tr><td>Marta</td><td>Hernandez</td><td>976</td></tr>
<tr><td>Martha</td><td>Larsson</td><td>1359</td></tr>
<tr><td>Martín </td><td>Sommer</td><td>1163</td></tr>
<tr><td>Martine </td><td>Rancé</td><td>699</td></tr>
<tr><td>Mary </td><td>Saveley</td><td>1428</td></tr>
<tr><td>Mary</td><td>Young</td><td>102</td></tr>
<tr><td>Matti</td><td>Karttunen</td><td>1051</td></tr>
<tr><td>Maurizio </td><td>Moroni</td><td>1280</td></tr>
<tr><td>Michael</td><td>Donnermeyer</td><td>401</td></tr>
<tr><td>Michael</td><td>Frick</td><td>787</td></tr>
<tr><td>Miguel</td><td>Barajas</td><td>572</td></tr>
<tr><td>Mihael</td><td>Holz</td><td>1078</td></tr>
<tr><td>Mike</td><td>Gao</td><td>596</td></tr>
<tr><td>Mike</td><td>Graham</td><td>1691</td></tr>
<tr><td>Mory</td><td>Kentary</td><td>692</td></tr>
<tr><td>Palle</td><td>Ibsen</td><td>882</td></tr>
<tr><td>Paolo </td><td>Accorti</td><td>843</td></tr>
<tr><td>Pascale </td><td>Cartrain</td><td>278</td></tr>
<tr><td>Paul </td><td>Henriot</td><td>1433</td></tr>
<tr><td>Peter</td><td>Ferguson</td><td>1926</td></tr>
<tr><td>Pirkko</td><td>Koskitalo</td><td>1110</td></tr>
<tr><td>Rachel</td><td>Ashworth</td><td>1778</td></tr>
<tr><td>Roland</td><td>Keitel</td><td>811</td></tr>
<tr><td>Roland </td><td>Mendel</td><td>532</td></tr>
<tr><td>Rosa</td><td>Salazar</td><td>730</td></tr>
<tr><td>Sarah</td><td>McRoy</td><td>1055</td></tr>
<tr><td>Sean</td><td>Clenahan</td><td>705</td></tr>
<tr><td>Steve</td><td>Frick</td><td>929</td></tr>
<tr><td>Steve</td><td>Thompson</td><td>511</td></tr>
<tr><td>Sue</td><td>Frick</td><td>1656</td></tr>
<tr><td>Sue</td><td>Taylor</td><td>514</td></tr>
<tr><td>Susan</td><td>Nelson</td><td>6366</td></tr>
<tr><td>Thomas </td><td>Smith</td><td>357</td></tr>
<tr><td>Tony</td><td>Snowden</td><td>1647</td></tr>
<tr><td>Valarie</td><td>Franco</td><td>695</td></tr>
<tr><td>Valarie</td><td>Thompson</td><td>954</td></tr>
<tr><td>Veysel</td><td>Oeztan</td><td>973</td></tr>
<tr><td>Violeta</td><td>Benitez</td><td>903</td></tr>
<tr><td>Wales</td><td>MacKinlay</td><td>1003</td></tr>
<tr><td>Wendy</td><td>Victorino</td><td>1236</td></tr>
<tr><td>William</td><td>Brown</td><td>988</td></tr>
<tr><td>Wing</td><td>Huang</td><td>1140</td></tr>
<tr><td>Yoshi </td><td>Tamuri</td><td>703</td></tr>
<tr><td>Yu</td><td>Choi</td><td>381</td></tr></table>
</body>
</html>



## 3.3

```mysql
SELECT customerName,sum(quantityOrdered) as 'amount' from customers inner join orders using(customerNumber) inner join
    orderdetails using (orderNumber)  WHERE customerName LIKE 'Volvo%' group by customerName ;
```



Result:

<!DOCTYPE html>
<html>
<head>
  <title></title>
</head>
<body>
<table border="1" style="border-collapse:collapse">
<tr><th>customerName</th><th>amount</th></tr>
<tr><td>Volvo Model Replicas, Co</td><td>647</td></tr></table>
</body>
</html>



## 3.4

```mysql
set @reportToManage:= (SELECT reportsTo from employees where  employeeNumber = 1611);
SELECT employeeNumber,firstName,lastName,reportsTo from employees where reportsTo =  @reportToManage;

```

<!DOCTYPE html>
<html>
<head>
  <title></title>
</head>
<body>
<table border="1" style="border-collapse:collapse">
<tr><th>employeeNumber</th><th>firstName</th><th>lastName</th><th>reportsTo</th></tr>
<tr><td>1611</td><td>Andy</td><td>Fixter</td><td>1088</td></tr>
<tr><td>1612</td><td>Peter</td><td>Marsh</td><td>1088</td></tr>
<tr><td>1619</td><td>Tom</td><td>King</td><td>1088</td></tr></table>
</body>
</html>

## 3.5

```mysql
SELECT  customerNumber, sum(amount) as total_payment from payments group by customerNumber order by customerNumber;
```



<!DOCTYPE html>
<html>
<head>
  <title></title>
</head>
<body>
<table border="1" style="border-collapse:collapse">
<tr><th>customerNumber</th><th>total_payment</th></tr>
<tr><td>103</td><td>22314.36</td></tr>
<tr><td>112</td><td>80180.98</td></tr>
<tr><td>114</td><td>180585.07</td></tr>
<tr><td>119</td><td>116949.68</td></tr>
<tr><td>121</td><td>104224.79</td></tr>
<tr><td>124</td><td>584188.24</td></tr>
<tr><td>128</td><td>75937.76</td></tr>
<tr><td>129</td><td>66710.56</td></tr>
<tr><td>131</td><td>107639.94</td></tr>
<tr><td>141</td><td>715738.98</td></tr>
<tr><td>144</td><td>43680.65</td></tr>
<tr><td>145</td><td>107446.50</td></tr>
<tr><td>146</td><td>130305.35</td></tr>
<tr><td>148</td><td>156251.03</td></tr>
<tr><td>151</td><td>177913.95</td></tr>
<tr><td>157</td><td>98509.25</td></tr>
<tr><td>161</td><td>104545.22</td></tr>
<tr><td>166</td><td>105420.57</td></tr>
<tr><td>167</td><td>97562.47</td></tr>
<tr><td>171</td><td>61781.70</td></tr>
<tr><td>172</td><td>86553.52</td></tr>
<tr><td>173</td><td>32198.69</td></tr>
<tr><td>175</td><td>95424.63</td></tr>
<tr><td>177</td><td>62361.22</td></tr>
<tr><td>181</td><td>72497.64</td></tr>
<tr><td>186</td><td>95546.46</td></tr>
<tr><td>187</td><td>148410.09</td></tr>
<tr><td>189</td><td>49898.27</td></tr>
<tr><td>198</td><td>21554.26</td></tr>
<tr><td>201</td><td>61167.18</td></tr>
<tr><td>202</td><td>70122.19</td></tr>
<tr><td>204</td><td>55577.26</td></tr>
<tr><td>205</td><td>93803.30</td></tr>
<tr><td>209</td><td>75859.32</td></tr>
<tr><td>211</td><td>45480.79</td></tr>
<tr><td>216</td><td>68520.47</td></tr>
<tr><td>219</td><td>7918.60</td></tr>
<tr><td>227</td><td>89909.80</td></tr>
<tr><td>233</td><td>68977.67</td></tr>
<tr><td>239</td><td>80375.24</td></tr>
<tr><td>240</td><td>71783.75</td></tr>
<tr><td>242</td><td>60483.36</td></tr>
<tr><td>249</td><td>82223.23</td></tr>
<tr><td>250</td><td>67659.19</td></tr>
<tr><td>256</td><td>58876.41</td></tr>
<tr><td>259</td><td>89223.14</td></tr>
<tr><td>260</td><td>66812.00</td></tr>
<tr><td>276</td><td>137034.22</td></tr>
<tr><td>278</td><td>127529.69</td></tr>
<tr><td>282</td><td>91655.61</td></tr>
<tr><td>286</td><td>90545.37</td></tr>
<tr><td>298</td><td>108777.92</td></tr>
<tr><td>299</td><td>69059.04</td></tr>
<tr><td>311</td><td>95706.15</td></tr>
<tr><td>314</td><td>62253.85</td></tr>
<tr><td>319</td><td>78432.16</td></tr>
<tr><td>320</td><td>101872.52</td></tr>
<tr><td>321</td><td>132340.78</td></tr>
<tr><td>323</td><td>154622.08</td></tr>
<tr><td>324</td><td>80556.73</td></tr>
<tr><td>328</td><td>38281.51</td></tr>
<tr><td>333</td><td>55190.16</td></tr>
<tr><td>334</td><td>103896.74</td></tr>
<tr><td>339</td><td>57939.34</td></tr>
<tr><td>344</td><td>46751.14</td></tr>
<tr><td>347</td><td>41506.19</td></tr>
<tr><td>350</td><td>71547.53</td></tr>
<tr><td>353</td><td>126983.19</td></tr>
<tr><td>357</td><td>56662.38</td></tr>
<tr><td>362</td><td>33533.47</td></tr>
<tr><td>363</td><td>116449.29</td></tr>
<tr><td>379</td><td>73533.65</td></tr>
<tr><td>381</td><td>29217.18</td></tr>
<tr><td>382</td><td>85060.00</td></tr>
<tr><td>385</td><td>87468.30</td></tr>
<tr><td>386</td><td>90143.31</td></tr>
<tr><td>398</td><td>105548.73</td></tr>
<tr><td>406</td><td>86436.97</td></tr>
<tr><td>412</td><td>66704.94</td></tr>
<tr><td>415</td><td>31310.09</td></tr>
<tr><td>424</td><td>69214.33</td></tr>
<tr><td>447</td><td>49967.78</td></tr>
<tr><td>448</td><td>76776.44</td></tr>
<tr><td>450</td><td>59551.38</td></tr>
<tr><td>452</td><td>51059.99</td></tr>
<tr><td>455</td><td>70378.65</td></tr>
<tr><td>456</td><td>29230.43</td></tr>
<tr><td>458</td><td>112440.09</td></tr>
<tr><td>462</td><td>88627.49</td></tr>
<tr><td>471</td><td>44920.76</td></tr>
<tr><td>473</td><td>25358.32</td></tr>
<tr><td>475</td><td>43748.72</td></tr>
<tr><td>484</td><td>50987.85</td></tr>
<tr><td>486</td><td>77726.59</td></tr>
<tr><td>487</td><td>42570.37</td></tr>
<tr><td>489</td><td>29586.15</td></tr>
<tr><td>495</td><td>65541.74</td></tr>
<tr><td>496</td><td>114497.19</td></tr></table>
</body>
</html>


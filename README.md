# PriceComparison
Post offer price comparison engine for e-commerce


Schema:


create table product (productId int NOT NULL AUTO_INCREMENT,websiteId int, priceRaw int, model varchar(50), colour varchar(10), year int, merchant varchar(20), PRIMARY KEY(productId));

OR

create table product (productId int NOT NULL AUTO_INCREMENT,websiteId int, priceRaw int, productKeywords varchar(100), PRIMARY KEY(productId));


create index index1 on product(productKeywords) using HASH;

create table offer (websiteId int, id int NOT NULL AUTO_INCREMENT,paymentOptionId int, vendorId int, cardVendorId int, minimumPurchase int DEFAULT 0, codeCoupon varchar(20), discountPercent int, discountAmount int, cashbackPercent int, cashbackAmount int, PRIMARY KEY(id) );

create table websites (websiteId int AUTO_INCREMENT, websiteName varchar(50), PRIMARY KEY(websiteId));

create table card_vendor (id int AUTO_INCREMENT, vendorName varchar(50), PRIMARY KEY(id));

create table vendor (id int AUTO_INCREMENT, vendorName varchar(50), PRIMARY KEY(id));

create table payment_option (id int AUTO_INCREMENT, paymentName varchar(50), PRIMARY KEY(id));

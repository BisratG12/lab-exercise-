# lab-exercise-
#include <iostream>
#define TAX_RATE 0.15;
int main (){
    std::cout<< "############## Welcome to product sales and inventory analyzer for a store ################\n\n";
    std::cout <<"######This program helps you to keep track product sales and manage inventory levels#######\n\n";
    std::cout << "#######################And be aware that C++ is a compiled language#######################\n\n";
    std::cout<<"********************************************************"<<"\n";

    std::cout<<"Product Categories:\n1 - Electronics\n2 - Groceries\n3 - Clothing\n4 - Stationery\n5 - Miscellaneous\n";
    std::string productName;
    int productCategory;
    int initialInventory;
    float productPrice;
    int numSoldItems;
    int newInventory{initialInventory};
    float totalSales;
    std::string inventoryStatus;
    auto totalSalesCopy = totalSales; 
    decltype(initialInventory) helperVariable;
    const float taxRate  = 0.15;
    std::string catagory;
    std::cout<<"Enter product name: ";
    std::getline(std::cin, productName);
    std::cout << "Enter  product category 1 to 5 : ";  
    std::cin >> productCategory; 
    std::cout << "Enter initial inventory quantity: ";  
    std::cin >> initialInventory;
    std::cout << "Enter product price: ";  
    std::cin >> productPrice;
    std::cout << "Enter number of items sold: ";  
    std::cin >> numSoldItems;
    newInventory= initialInventory-numSoldItems;
    totalSales = numSoldItems*productPrice;
    std::cout<<"************************************\n\n**************Status*****************\n\n";
    (initialInventory<10) ? std::cout<< "Low Inventory\n": std::cout<<"Sufficient Inventory\n";
    if (productCategory>=1&&productCategory<=5){
        std::cout<<"Product category is valid\n";
         }
    else{
        do{
        std::cout<<"Product category is invalid\nPlease enter a number between 1 and 5: ";
        std::cin >> productCategory; 
        }while(productCategory<1||productCategory>5);}
    switch (productCategory)
    {
        case 1: catagory="Electronics";
        std::cout<< "Category 1: Electronics\n";
        break;
        case 2: catagory="Groceries";
        std::cout<< "Category 2: Groceries\n";
        break; 
        case 3: catagory="Clothing";std::cout<<"Category 3: Clothing\n";
        break;
        case 4:catagory="Stationery"; std::cout<<"Category 4: Stationery\n";
        break;
        case 5: catagory="Miscellaneous";std::cout<<"Category 5: Miscellaneous\n";
        break;     
    default: std::cout<<"No item";
        break;
    }
    int i ;
    std::cout <<"######### Receipt ##########\n\n";
    for (i=1 ; i<=numSoldItems;i++){
        
        std::cout<<"Item "<<i<<":               "<<" "<<productPrice<<"ETB\n";
        std::cout<<"Tax:             "<<productPrice*taxRate<<"ETB\n";
    }
    std::cout<< "\n\n               "<<"Total: " << totalSales <<"ETB\n";
    std::cout<< "                    "<<"Tax: " << numSoldItems*taxRate *productPrice<<"ETB\n";
    std::cout<< "          "<<"Total price: " << totalSales+ numSoldItems*taxRate*productPrice<<"ETB\n";
    std::cout<<"Tax rates from the preprocessor constant: "<<0.15*100<<"%\n\n";
    std::cout<<"Tax rates from the const variable: "<<0.15*100<<"%\n\n";
    std::cout<<"Product name: "<<productName<<"\n\n";
    std::cout<<"Product category: "<<catagory<<"\n\n";
    std::cout << "initial inventory:"<<initialInventory<<"\n\n";
    std::cout <<"Product price: "<<productPrice<<"\n\n";
    std::cout << "Number of items sold: "<<numSoldItems<<"\n\n";
    std::cout<<"New inventory: "<<newInventory<<"\n\n";
    std::cout << "Total sales: "<<totalSales<<"\n\n";
    std::cout<<"Inventory status: ";(initialInventory<10) ? std::cout<< ""<<"Low Inventory\n\n": std::cout<<"Sufficient Inventory\n\n";
    std::cout<<"Total Sales Amount (Copy using `auto`): $"<<totalSales<<"\n";
    std::cout<<"Initial Inventory (Using `decltype`): "<<initialInventory<<"\n";
    std::cout<<"\n#########################################################\nProcessing complete! Thank you for using the Product Sales and Inventory Analyzer.";







    


    return 0;
}

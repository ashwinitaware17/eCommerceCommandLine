Main class App.java 

```java
public class App 
{
    public static void main( String[] args ){
        
        println("Welcome to ..");
        println("What you would like to do ..");
        println("1. Register");
        println("2. Login");
        Scanner sc = new Scanner(System.in());
        int choice = Integer.parseInt(sc.next());
        switch(ch){
                2: 
               		println("Enter usename : ");
                	String userName = sc.next();
        	   		println("Enter pwd : ");
                	String pwd = sc.next();
                	LoginInput input = new LoginInput(userName, pwd);
                    LoginService loginService = new LoginService();
                	boolean valid = loginService.validateUser(input);
                	if(valid){
                        println("What you would like to do ..");
        				println("1. Purchase products");
        				println("2. Exit");
                        int operation = Integer.parseInt(sc.next());
                        swich(operation){
                            case 1 :
                                   ProductService productService = new ProductService();
                            	   List<ProductDetails> productsList = productService.getAllProducts();
                            	   println("Product details");
                            	   println("Product Id| Name | Description | Price");
                            	   productsList.forEach(p ->
                                                       println(p.getId+" , "+p.getName+" , "+p.getDescription+" , "+p.getPrice()));
                            	   Hashmap<String, ProductDetails> productIdToProductDetailsMap = new HashMap();
                            productIdToProductDetailsMap.put(1, productDetails);
                            //create this map on your own
                            // {  
                            //  id -> ProductDetails{id, name, price, quantity}
                            //  1 -> ProductDetails{1, "Dove Soap", 40, 50},
                            //  2 -> ProductDetails{1, "Dove Shampoo", 100, 40},  
                            // }
                                   println("Which product you would like to purchase");
                            	   int productId = Integer.parseInt(sc.next());
                                   println("Please specify quantity");
                                   int productQuantity = Integer.parseInt(sc.next());
                                   int productPrice = productIdToProductDetailsMap.get(productId).getPrice();
                                   int totalPrice = productPrice * productQuantity;
                            	   println("Total price is:  "+totalPrice)
                                   println("Adding this product to cart");
                                   ProductPurchaseDetails productPurchase = new ProductPurchaseDetails(productId, productQuantity, productPrice, totalPrice);
                            	   List<ProductPurchaseDetails> cartDetails = new ArrayList();
                            	   cartDetails.add(ProductPurchaseDetails);
                                   
                            	   println("Do you want to check out ? (Y/N)");
                                   String checkOut = sc.next();
                            	   if(checkOut == 'Y'){
                                  		productService.updateProductsQuantity(ProductPurchaseDetails);
                                       println("Thanks for shopping");
                                   }   		
                        }
                    }else{
                        println("Invalid username or password");
                    }
                   
                
        }
            
    }
        
        
```



Model classes

Create package `com.ashwini.projects.ecommercecommandline.model`

```java
package com.ashwini.projects.ecommercecommandline.model;

public class LoginInput{
    private String userName;
    private String password;
    public LoginInput(String userName, String password){
        this.userName = userName;
        this.password = password;
    }
}

public class ProductDetails{
    private String id;
    private String name;
    private String description;
    private int quantity;
    private double price;
    public ProductDetails(String id, String name, String description, int quantity, double price){
        //initialize here same as LoginInput class
    }
}

public class ProductPurchaseDetails{
    private String id,
    private double price;
    private int quantity;
    private double totalPrice;
    public ProductPurchaseDetails(String id, double price, int quantity, double totalPrice){
        //initialize all fields here, same LoginInput class
    }
}
```





Service classes

create package `com.ashwini.projects.ecommercecommandline.service`

```java
public class LoginService{
    public boolean validateUser(LoginInput loginInput){
        UserService userService = new UserService();
        UserDetails userDetails = userService.findByUserName(userService.getUserName());
        if(userDetails.getPassword().equals(loginInput.getPassword())){
            return true;
        }
        return false;
    }
}

public class UserService{
    UserDetails findByUserName(String userName){
        String url
            = "jdbc:mysql://localhost:3306/users"; // table details
        String username = "root"; // MySQL credentials
        String password = "root";
        String query
            = "select * from users where id = ?"; // query to be run
        Class.forName(
            "com.mysql.cj.jdbc.Driver"); // Driver name
        Connection con = DriverManager.getConnection(
            url, username, password);
        System.out.println(
            "Connection Established successfully");
        PreparedStatement stmt=con.prepareStatement(query);  
stmt.setInt(1,username);//1 specifies the first parameter in the query  
        ResultSet rs
            = st.executeQuery(query); // Execute query
        rs.next();
        String id = rs.getString("Id"); // Retrieve name from db
        String name = rs.getString("Name"); // Retrieve name from db
        String password = rs.getString("Password"); // Retrieve name from db
        UserDetails userDetail = new UserDetails(id, name, password);
        return userDetail;
	}
}

public class ProductService{
    
    List<ProductDetails> getAllProducts(){
        
        //DB connection
        // return all products
    }
    
    public void updateProductDetails(List<ProductPurchaseDetails> list){
        //DB connection
        // update product details
    }
}
```


# ytyftyftyu
package com.cg.ems.ui;

import java.util.List;
import java.util.Scanner;

import com.cg.ems.dto.Employee;
import com.cg.ems.exception.EmployeeException;
import com.cg.ems.dto.Employee;
import com.cg.ems.exception.EmployeeException;
import com.cg.ems.dto.Employee;
import com.cg.ems.exception.EmployeeException;
import com.cg.ems.service.EmployeeService;
import com.cg.ems.service.EmployeeServiceImpl;
import com.cg.pms.dto.Product;
import com.cg.pms.exception.ProductException;
import com.cg.pms.service.IProductService;
import com.cg.pms.service.ProductServiceImpl;




public class MyTest {

	
	public static void main(String[] args) {
		// TODO Auto-generated method stub
int choice = 0;
//runtime polymorphism
EmployeeService emp1service = new EmployeeServiceImpl();//prodservice is reference

do{
	printDetail();
	Scanner scr= new Scanner(System.in);
	System.out.println("enter the choice...");
	choice = scr.nextInt();
	
	switch(choice){
	case 1://Add
		int msg =0;
		System.out.println("enter the productId");
		int emp1Id = scr.nextInt();
		System.out.println("enter the product name");
		String emp1me = scr.next();
		System.out.println("enter the price");
		double emp1Price = scr.nextDouble();
		System.out.println("enter the description");
		String emp1Des = scr.next();
		
		Employee emp1 = new Employee();
	
		emp1.setId(empId);
		emp1.setName(emp1Name);
		emp1.setSalary(emp1Salary);
		
		
		//calling service layer...
		
		try {
			msg = emp1service.addProduct(prod);
		} catch (EmployeeException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
			System.out.println(e.getMessage());
		}
		
		if(msg==1){
			System.out.println("data inserted.....");
		}
		break;
	case 2://showAll
		List<Employee> myemp1=null;
		try {
			myemp1 = emp1service.showall();
		} catch (EmployeeException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
			System.out.println(e.getMessage());
		}
		
		for (Employee employee : myemp1) {
		System.out.println("id is"+employee.getId());	
		System.out.println("name is:"+employee.getName());
		System.out.println("salary is:"+employee.getSalary());
		
		
		}
		break;
	case 3://Search
		System.out.println("Enter Product Id.");
		int id=scr.nextInt();
		Employee mySearchProd = null;
		try {
			myemp1 = emp1service.searchProduct(id);
		} catch (EmployeeException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
			System.out.println(e.getMessage());
		}
	System.out.println("id is"+myemp1.getId());	
	System.out.println("name is:"+myemp1.getName());
	System.out.println("salary is:"+myemp1.getSalary());
	
	
		break;
	case 4://remove	
		break;
	case 5://exit
		System.exit(0);
		break;
		
	}
	
}while(choice==5);	
	}
public static void printDetail(){
	
	System.out.println("********");
	System.out.println("1. ADD Product");
	System.out.println("2. Show All Product");
	System.out.println("3. Search Product");
	System.out.println("4. Remove Product");
	System.out.println("5. Exit");
	System.out.println("********");
}
}



	
		
	}


	

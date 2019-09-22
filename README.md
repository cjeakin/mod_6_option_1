# mod_6_option_1
module 6 of capstone-option 1- using existing program
class Car_Inventory:
    dealer_list = []
    def __init__(self, make, model, color, year, mileage):
        self.make = make
        self.model = model
        self.color = color
        self.year = year
        self.mileage = mileage
        Car_Inventory.dealer_list.append(self)
    def add_vehicle(vehicle):
        Car_Inventory.dealer_list.append(vehicle)
    def delete_vehicle(vehicle_name):
        for vehicle in Car_Inventory.dealer_list:
            if vehicle.get_make()==vehicle_name:
                Car_Inventory.dealer_list.remove(vehicle)
    def delete_auto(self):
        if self in Car_Inventory.dealer_list:
            Car_Inventory.dealer_list.remove(self)    
    
    def get_model(self) :
        return self.model
    def get_color(self) :
        return self.color
    def get_make(self) :
        return self.make
    def get_mileage(self) :
        return self.mileage
    def get_year(self) :
        return self.year
    
    def set_model(self, value):
        self.model = value
    def set_make(self, value):
        self.make = value
    def set_year(self, value):
        self.year = value
    def set_color(self, value):
        self.color = value
    def set_mileage(self, value):
        self.mileage = value
    def __str__(self):
        return "Make: " + self.get_make() + "Model: " + str(
            self.get_model()) + "Color: " + str(self.get_color()) + "Year: " + str(self.get_year()) + "Mileage: " + str(
            self.get_mileage())
def menu():
    print("Please Select Option:")
    print("1. Add Vehicle to Inventory")
    print("2. Delete Vehicle from Inventory")
    print("3. EXIT PROGRAM")
    option=input("Enter Numeric Selection:")
    return option

def main():
    while True:
        option=int(menu())
        if option==1:
            print("Enter New Vehicle Inventory Number:")
            inventory_number=input()
            make=input("Enter Make:")
            model=input("Enter Model:")
            year=input("Enter Year:")
            color=input("Enter Color:")
            mileage=input("Enter Mileage:")
            vehicle = Car_Inventory(inventory_number, model, color, year, mileage)
        elif option==2:
            name=input("Enter Vehicle Inventory Number:")
            Car_Inventory.delete_vehicle(inventory_number)
            print("Vehicle Deleted From Inventory")
        elif option==3:
            break

main()

with open("Output.txt", "w") as text_file:
    print(Car_Inventory, file=text_file)

# Inventroy-Managment-Sysytem
This project is about Mini Inventory.


class Inventory:
    def __init__(self):
        self.items = []

    def add_item(self, item_no, item_name, unit, price_per_unit):
        item = [item_no, item_name, unit, price_per_unit]
        self.items.append(item)

    def update_item(self, item_no, unit=None, price_per_unit=None):
        for item in self.items:
            if item[0] == item_no:
                if unit is not None:
                    item[2] = unit
                if price_per_unit is not None:
                    item[3] = price_per_unit
                return
        print(f"Item with item_no {item_no} not found.")

    def delete_item(self, item_no):
        for item in self.items:
            if item[0] == item_no:
                self.items.remove(item)
                return
        print(f"Item with item_no {item_no} not found.")

    def show_items(self):
        items_dict = {}
        for item in self.items:
            item_no = item[0]
            item_info = {
                "item_name": item[1],
                "unit": item[2],
                "price_per_unit": item[3]
            }
            items_dict[item_no] = item_info
        return items_dict


# Example usage:
inv = Inventory()

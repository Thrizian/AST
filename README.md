AST
===

Althuizen Solar Technology management software.

the plan of this software is to build a CRUD database that stores customers/products/packages/orders and a tax rate.

Below an overview of the planned database tables

# Tables
Client				has_many_orders

client_id				automatic
company				Bolean
company_contact		string
Title					string
Prefix				string
Suffix				string
surname				string
street				string
number				integer
addition				string
roomno				nummeric
zipcode				alphanummeric
place				string
country				string
birthdate				date
iban					string
created_at			automatic
updated_at			automatic
email				string
phone				string
cell_phone			string

Order			"	has_many 	:packages
					belongs_to 	:client
					has_one 	 	:btw"
order_id				nummeric
order_no				string
package				array
price					integer
discount				integer
payment_check		bolean
confirmation_check		bolean
notes				text
approval_installation	bolean
approval_payment		bolean
approval_completed	bolean
approval_payment_up_front	bolean
	
Products			"	belongs_to :order
					has_many :parts"
product_id			automatic
name				string
storage				integer
price_buy				integer
price_sell				integer
prerequisites			array
availability			bolean
warranty				integer
product_warranty		integer
colour				black or blue
length				integer (in mm)
width				integer (in mm)
roof					flat or sloped
wattage				integer (in watts)
	
BTW					belongs_to: product
sale					integer
integer				integer
mechanic				integer
electrician			integer
	
package			"	has_many	:products
					has_one		:btw
					belongs_to: order"
package_id			automatic
package_name		string
montage				bolean
electricien			bolean
roof					flat/sloped
products				array

# below here are some formulas that will be used to calculate panel building and materials needed for orders

variabelen	
Tussenruimte= 20	
restruimte= 90	
p=paneel	

berekeningen per rij	lengte + p-1 x tussenruimte + restruimte x 2	
montagerail staand	breedte + p-1 x tussenruimte + restruimte x 2	
montagerail liggend	4	
eindklemmen	p-1x2	
tussenklemmen	montagerail(meters)x2.5x1.10	
dakhaken	is gelijk aan aantal dakhaken.	
moer M10	is gelijk aan aantal dakhaken.	
bout M10	eindklemmen+tussenklemmen	
railmoer	if dak = plat landscape and blue 30mm else if dak is plat landscape and black 25mm else if blue 25mm and black 20mm	
Imbusbouten M8		
Stekkers	if  plat landscape paneelx5.5 else if plat portrait paneel x 8	
Stoeptegels	if plat dak paneel +1	.. Rij(en) van ... Panelen
plat dak landscape	paneelx1.4+1	.. Rij(en) van ... Panelen
plat dak steun portrait	if landscape plat dak (lengte + p-1 x tussenruimte + restruimte x 2) elseif plat dak portrait (breedte + p -1 x tussenruimte + restruimte x 2)	.. Rij(en) van ... Panelen
L profiel		.. Rij(en) van ... Panelen
		
		
soort paneel		
platdak/pannendak	landscape/portait	
platdak/pannendak	landscape/portait	
platdak/pannendak	landscape/portait	
platdak/pannendak	landscape/portait	

# Designing for Surface-Mount components
These are my notes for how to do a Surface-Mount design with KiCad and JLCPCB.

## Component Selection
Assuming you've got a base design, the first complication for going SMT is to figure out which components you want to use.  JLCPCB's parts library can be found here:
https://jlcpcb.com/client/index.html#/parts

For each component, there are a few key attributes:  
### Cost
They'll list the "by-part" cost, and also whether the part is "basic" or "extended".  Extended part will cost an extra $1 for the whole run...but that gets spread across your entire order.  Here are a couple examples:  
- Lets say you are using an extended IC that has a base price of $2 each.  You have one of those per board, and are doing a run of 5 boards.  That means your total cost for those ICs is $2x5 + $1 or $11...or, looking at it another way, using an extended part added 20c per board to the order.
-  Now consider a board with 8 extended LEDs, each with a base price of 10c.  You are doing a run of 10 boards.  The LED component price is going to be 10c x 8 x 10 + $1, or $9...meaning your actual cost per LED went up to 11.25c

### Footprint
Each part has a given footprint, and you can double-check that footprint's dimensions in the KiCad footprint library.  When doing the KiCad schematic, you'll assign those footprints to the appropriate schematic component.  Export the netlist as normal.

## Layout
Now that you've got your components selected, you need to do the full board layout.  This isn't all that different from a through-hole layout...except that you should have the approprite solder-paste/mask layers done for you automatically based on the footprints in quesiton.  

JLCPCB will only populate one side of the board, so pick which side you want all your surface mount components on...and lay out the board and run traces as per normal.

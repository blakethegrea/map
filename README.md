map
===
//var:L x1 y1 x2 y2 Lx Ly yd1 xd1 corner corner1x
//corner1y corner3x corner3y


var mapsizes=[256,512,1024,2048];
//length of maps in blocks//

var maps= prompt
("What zoom step map do you want?(1,2,3,4)");

var L= mapsizes[maps-1];

alert("gather two cordinates at the corners of where you want your map to cover. These points should probably be opposite of eachother(northwest and southeast, southwest northeast)");
var x1= prompt
("What is the x of your first selection corner(ie: 76,y1)");

var y1= prompt
("What is the y of your first selection corner(ie: x1,83)");
var x2= prompt
("what is the x of your second selection corner(ie: -360,y2)");

var y2= prompt
("what is the y of your second selection corner(ie: x2,951)");

var Lx= Math.ceil((Math.abs(x1-x2))/L);
//ceiling of (distance between x1 and x2 over L)
console.log("Lx="+Lx);

var Ly= Math.ceil((Math.abs(y1-y2))/L);
//ceiling of (distance between y1 and y2 over L)
console.log("Ly="+Ly);
console.log("The nubmer of maps you will need is:"+Ly*Lx);

if(x1<x2)
{ var xd1="w"}

else
{ var xd1="e"}



if(y1<y2)
{ var yd1="n";}

else
{ var yd1="s";}
/////////////////////////////////////////////////////
//^^^^gives the direction of the first x and y
/////////////////////////////////////////////////////

var corner="0";
/////////////////////////////////////////////////////
//^^^defines corner so it can be changed
/////////////////////////////////////////////////////

if (yd1+xd1==="nw")
{var corner=1;}
else if(yd1+xd1==="sw")
{var corner=3;}
else if(yd1+xd1==="ne")
{var corner=3;}
else if(yd1+xd1==="se")
{var corner=1;}
///////////////////////////////////////////////////////
//^^^combines variables to allow to give a direction of //where first cordinate is in relation to other coord
//////////////////////////////////////////////////////
var corner3x=0;
var corner3y=0;
var corner1x=0;
var corner1y=0;
////////////////////////////////////////////////////////
//defining variables so i can use them
////////////////////////////////////////////////////////

if (yd1+xd1==="nw")
{ 
    corner1x=x1;
    corner1y=y1;
    console.log("corner1:"+corner1x,corner1y);
}
else if(yd1+xd1==="sw")
{
    corner3x=x1;
    corner3y=y1;
    console.log("corner3:"+corner3x,corner3y);
}
else if(yd1+xd1==="se")
{
    corner1x=x2;
    corner1y=y2;
    console.log("corner1:"+corner1x,corner1y);
}
else if(yd1+xd1==="ne")
{
    corner3x=x2;
    corner3y=y2;
    console.log("corner3:"+corner3x,corner3y);
}
//////////////////////////////////////////////////////////
//^^tells what cordinate set(first or second) is in 
//corner 3 or corner 1
//////////////////////////////////////////////////////////
var xofmc=0;
var yofmc=0;

//////////////////////////////////////////////////////////
// xofmc is "x of first map center"
// yofmc is "y of first map center"
//////////////////////////////////////////////////////////

if (corner===1)
{
    xofmc=corner1x+(L/ 2);
    yofmc=corner1y+(L/ 2);
}
else if (corner===3)
{
    xofmc=corner3x+(L/2);
    yofmc=corner3y-(L/2);
}
//////////////////////////////////////////////////////////// positioning it so their cordinate in the third or first
// corner will actually be a corner of first map
//////////////////////////////////////////////////////////
console.log(xofmc);
console.log(yofmc);



























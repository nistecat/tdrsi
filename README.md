# tdrsi
Tom Demark RSI Indicator
study(title="My TD RSI", shorttitle="My TD RSI")
src = input(close), len = input(4, minval=1, title="Length")
up = rma(max(change(src), 0), len)
down = rma(-min(change(src), 0), len)
rsi = down == 0 ? 100 : up == 0 ? 0 : 100 - (100 / (1 + up / down))
pointup=rsi[1]>rsi[2] and rsi[1]>rsi
pointdown=rsi[1]<rsi[2] and rsi[1]<rsi

plot(rsi, color=purple, linewidth=1)
plot(rsi, color=purple, linewidth=1)
plotshape(pointup,style=shape.xcross, color=green, location=location.top, offset=-1 )
plotshape(pointdown,style=shape.xcross, color=red, location=location.top, offset=-1 )

band1 = hline(0, linestyle=solid)
band2 = hline(38, linestyle=dashed)
band3 = hline(50, linestyle=solid)
band4 = hline(62, linestyle=dashed)
band5 = hline(100, linestyle=solid)
band6 = hline(10, linestyle=solid)
band7 = hline(15, linestyle=solid)
band8 = hline(20, linestyle=solid)
band9 = hline(25, linestyle=solid)

fill(band2, band3, color=red, transp=90)
fill(band3, band4, color=green, transp=90)




transp=input(0)
Numbers=input(true)

TD = rsi > rsi[4] ?nz(TD[1])+1:0
TS = rsi < rsi[4] ?nz(TS[1])+1:0

TDUp = TD - valuewhen(TD < TD[1], TD , 1 )
TDDn = TS - valuewhen(TS < TS[1], TS , 1 )
plotshape(Numbers?(TDUp==1?true:na):na,style=shape.triangledown,text="1",color=green,location=location.absolute,transp=transp)
plotshape(Numbers?(TDUp==2?true:na):na,style=shape.triangledown,text="2",color=green,location=location.absolute,transp=transp)
plotshape(Numbers?(TDUp==3?true:na):na,style=shape.triangledown,text="3",color=green,location=location.absolute,transp=transp)
plotshape(Numbers?(TDUp==4?true:na):na,style=shape.triangledown,text="4",color=green,location=location.absolute,transp=transp)
plotshape(Numbers?(TDUp==5?true:na):na,style=shape.triangledown,text="5",color=green,location=location.absolute,transp=transp)
plotshape(Numbers?(TDUp==6?true:na):na,style=shape.triangledown,text="6",color=green,location=location.absolute,transp=transp)
plotshape(Numbers?(TDUp==7?true:na):na,style=shape.triangledown,text="7",color=green,location=location.absolute,transp=transp)
plotshape(Numbers?(TDUp==8?true:na):na,style=shape.triangledown,text="8",color=green,location=location.absolute,transp=transp)
plotshape(Numbers?(TDUp==9?true:na):na,style=shape.triangledown,text="9",color=green,location=location.absolute,transp=transp)
plotshape(Numbers?(TDUp==10?true:na):na,style=shape.triangledown,text="10",color=green,location=location.absolute,transp=transp)
plotshape(Numbers?(TDUp==11?true:na):na,style=shape.triangledown,text="11",color=green,location=location.absolute,transp=transp)

plotshape(Numbers?(TDDn==1?true:na):na,style=shape.triangleup,text="1",color=red,location=location.absolute,transp=transp)
plotshape(Numbers?(TDDn==2?true:na):na,style=shape.triangleup,text="2",color=red,location=location.absolute,transp=transp)
plotshape(Numbers?(TDDn==3?true:na):na,style=shape.triangleup,text="3",color=red,location=location.absolute,transp=transp)
plotshape(Numbers?(TDDn==4?true:na):na,style=shape.triangleup,text="4",color=red,location=location.absolute,transp=transp)
plotshape(Numbers?(TDDn==5?true:na):na,style=shape.triangleup,text="5",color=red,location=location.absolute,transp=transp)
plotshape(Numbers?(TDDn==6?true:na):na,style=shape.triangleup,text="6",color=red,location=location.absolute,transp=transp)
plotshape(Numbers?(TDDn==7?true:na):na,style=shape.triangleup,text="7",color=red,location=location.absolute,transp=transp)
plotshape(Numbers?(TDDn==8?true:na):na,style=shape.triangleup,text="8",color=red,location=location.absolute,transp=transp)
plotshape(Numbers?(TDDn==9?true:na):na,style=shape.triangleup,text="9",color=red,location=location.absolute,transp=transp)
plotshape(Numbers?(TDDn==10?true:na):na,style=shape.triangleup,text="10",color=red,location=location.absolute,transp=transp)
plotshape(Numbers?(TDDn==11?true:na):na,style=shape.triangleup,text="11",color=red,location=location.absolute,transp=transp)

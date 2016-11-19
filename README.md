# OlyaKrugley
program Project1; 

{$mode objfpc}{$H+} 

uses 
{$IFDEF UNIX}{$IFDEF UseCThreads} 
cthreads, 
{$ENDIF}{$ENDIF} 
Classes 
{ you can add units after this }; 

var x,y,n,a,b,f,fa,fb:real; m:integer; 
function integral(x,y,n:real;i:integer):real; 
var j:integer;p:real=1; 
begin 
if i>1 then 
begin 
for j:=1 to i do p:=p*y; 
writeln(#13#10,'i=',i,' integral:=',((p*exp(x*y))/x-n/x):-7:3,' integral(',x:-5:3,',',y:-5:3,',',n:-5:3,',',i-1,')'); 
integral:=(p*exp(x*y))/x-n/x*integral(x,y,n,i-1); 
writeln('i=',i,' integral=',integral:-7:3); 
end 
else 
begin 
integral:=exp(x*y)/(x*x)*(x*y-1); 
writeln('i=',i,' integral=',integral:-7:3); 
end; 
end; 
begin 
repeat 
writeln('Vvedite a<b'); 
readln(a,b); 
until a<b; 
repeat 
writeln('Vvedite m>=1'); 
readln(m); 
until m>=1; 
writeln('Vvedite x,y,n'); 
readln(x,y,n); 
writeln(#13#10,fb:-7:3,'-',fa:-7:3,'=',f:-7:3); 
readln; 
end.

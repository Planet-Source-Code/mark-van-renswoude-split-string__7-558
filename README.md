<div align="center">

## Split string


</div>

### Description

This code simply splits a string into pieces using any delimiter and returns an array. Enjoy!It seems PSC has messed up my code, to view a nicely formatted and color coded version of this code go to http://x2software.net/viewarticle.php?id=5
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Mark van Renswoude](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/mark-van-renswoude.md)
**Level**          |Intermediate
**User Rating**    |5.0 (10 globes from 2 users)
**Compatibility**  |Delphi 5, Delphi 4, Pre Delphi 4
**Category**       |[String Manipulation](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/string-manipulation__7-5.md)
**World**          |[Delphi](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/delphi.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/mark-van-renswoude-split-string__7-558/archive/master.zip)





### Source Code

```
type
 TSplitArray = array of String;
function Split(const Source, Delimiter: String): TSplitArray;
var
 iCount: Integer;
 iPos: Integer;
 iLength: Integer;
 sTemp: String;
 aSplit: TSplitArray;
begin
 sTemp := Source;
 iCount := 0;
 iLength := Length(Delimiter) - 1;
 repeat
 iPos := Pos(Delimiter, sTemp);
 if iPos = 0 then
 break
 else begin
 Inc(iCount);
 SetLength(aSplit, iCount);
 aSplit[iCount - 1] := Copy(sTemp, 1, iPos - 1);
 Delete(sTemp, 1, iPos + iLength);
 end;
 until False;
 if Length(sTemp) > 0 then begin
 Inc(iCount);
 SetLength(aSplit, iCount);
 aSplit[iCount - 1] := sTemp;
 end;
 Result := aSplit;
end;
```


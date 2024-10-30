# Sumar dos números

```
procedure TForm1.Button1Click(Sender: TObject);
var
  numero1, numero2, resultado : Double;

begin
  numero1 := StrToFloat(Edit1.Text);
  numero2 := StrToFloat(Edit2.Text);
  resultado := numero1 + numero2;
  Label1.Caption := FloatToStr(resultado);
end;

end.
```

```
FDConnection

Database=C:\ruta\a\tu_base_de_datos.sqlite
LockingMode=Normal
Synchronous=Full
```

```
uses
  FireDAC.Comp.Client, FireDAC.Stan.Def, FireDAC.Stan.Param;

procedure TForm1.FormCreate(Sender: TObject);
begin
  FDConnection1.DriverName := 'SQLite';
  FDConnection1.Params.Database := 'C:\ruta\a\tu_base_de_datos.sqlite';
  FDConnection1.Connected := True;

  FDQuery1.SQL.Text := 'SELECT * FROM NombreTabla';
  FDQuery1.Open;
end;
```

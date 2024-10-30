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


# trukos-delphi

# Hello World
```

unit Unit1;

interface

uses
        Winapi.Windows, Winapi.Messages, System.SysUtils, System.Variants,
        System.Classes, Vcl.Graphics,
        Vcl.Controls, Vcl.Forms, Vcl.Dialogs, Vcl.StdCtrls;

type
        TForm1 = class(TForm)
                Edit1: TEdit;
                Edit2: TEdit;
                Button1: TButton;
                Edit3: TEdit;
                procedure Button1Click(Sender: TObject);
        private
                { Private declarations }
        public
                { Public declarations }
        end;

var
        Form1: TForm1;

implementation

{$R *.dfm}

procedure TForm1.Button1Click(Sender: TObject);

var
        // Declaracion de Variables
        a: real;
        b: real;
        c: real;

begin
        // Calculo
        a := StrToFloat(Edit1.Text);
        b := StrToFloat(Edit2.Text);
        c := a + b;

        // resultado
        Edit3.Text := FloatToStr(c);

end;

end.


```


# Tipos de Datos
```
var
  num: Integer;
  decimalNumber: Real;
  letter: Char;
  name: String;
  isActive: Boolean;
  smallNumber: Byte;
  wordNumber: Word;
  bigNumber: LongInt;
  singlePrecision: Single;
  doublePrecision: Double;
```

# Arreglos
```
program ArrayExample;

var
  arr: array[1..5] of Integer;
  i: Integer;

begin
  { Asignamos valores al arreglo }
  arr[1] := 10;
  arr[2] := 20;
  arr[3] := 30;
  arr[4] := 40;
  arr[5] := 50;

  { Recorremos el arreglo e imprimimos cada elemento }
  for i := 1 to 5 do
  begin
    writeln('Elemento ', i, ': ', arr[i]);
  end;
end.
```


# Arreglos
```
program DynamicArrayExample;

type
  TIntArray = array of Integer;  { Declaramos un tipo de arreglo dinámico }

var
  arr: TIntArray;
  i, n: Integer;

begin
  { Solicitamos el tamaño del arreglo }
  write('Ingrese el tamaño del arreglo: ');
  readln(n);

  { Configuramos el tamaño del arreglo dinámico }
  SetLength(arr, n);

  { Asignamos valores al arreglo }
  for i := 0 to n - 1 do
  begin
    arr[i] := (i + 1) * 10;  { Ejemplo: llenamos con múltiplos de 10 }
  end;

  { Recorremos el arreglo e imprimimos cada elemento }
  for i := 0 to n - 1 do
  begin
    writeln('Elemento ', i + 1, ': ', arr[i]);
  end;
end.
```


# POO uso de clases
```
program IfElseExample;

var
  num: Integer;

begin
  write('Ingrese un número: ');
  readln(num);

  if num > 0 then
    writeln('El número es positivo')
  else if num < 0 then
    writeln('El número es negativo')
  else
    writeln('El número es cero');
end.
```

# IF ELSE
```
program ClasePersona;

type
  TPersona = class
  private
    Nombre: String;
    Edad: Integer;
  public
    constructor Create(aNombre: String; aEdad: Integer);
    procedure MostrarInfo;
  end;

{ Implementación de los métodos de la clase }

constructor TPersona.Create(aNombre: String; aEdad: Integer);
begin
  Nombre := aNombre;
  Edad := aEdad;
end;

procedure TPersona.MostrarInfo;
begin
  writeln('Nombre: ', Nombre);
  writeln('Edad: ', Edad);
end;

{ Programa principal }

var
  persona: TPersona;

begin
  persona := TPersona.Create('Juan', 30);
  persona.MostrarInfo;
  persona.Free;  { Liberamos la memoria }
end.
```

# CASE
```
program CaseExample;

var
  dia: Integer;

begin
  write('Ingrese un número de 1 a 7 para el día de la semana: ');
  readln(dia);

  case dia of
    1: writeln('Lunes');
    2: writeln('Martes');
    3: writeln('Miércoles');
    4: writeln('Jueves');
    5: writeln('Viernes');
    6: writeln('Sábado');
    7: writeln('Domingo');
  else
    writeln('Número no válido. Ingrese un número entre 1 y 7.');
  end;
end.
```

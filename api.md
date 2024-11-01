# GET
```
rogram RestApiGetExample;

uses
  fphttpclient, fpjson, jsonparser, SysUtils;

var
  httpClient: TFPHTTPClient;
  response: String;
  jsonData: TJSONData;
begin
  httpClient := TFPHTTPClient.Create(nil);
  try
    // Realizar la solicitud GET
    response := httpClient.Get('https://jsonplaceholder.typicode.com/posts/1');
    
    // Parsear la respuesta JSON
    jsonData := GetJSON(response);
    writeln('Respuesta de la API:', jsonData.AsJSON);
    
    // Acceder a un campo específico
    writeln('ID del Post:', jsonData.FindPath('id').AsString);
    writeln('Título:', jsonData.FindPath('title').AsString);
    
    jsonData.Free;
  except
    on E: Exception do
      writeln('Error al hacer la solicitud GET: ', E.Message);
  end;
  httpClient.Free;
end.
```

# POST
```
program RestApiPostExample;

uses
  fphttpclient, fpjson, jsonparser, SysUtils;

var
  httpClient: TFPHTTPClient;
  jsonToSend, response: String;
  jsonData: TJSONObject;
begin
  httpClient := TFPHTTPClient.Create(nil);
  jsonData := TJSONObject.Create;
  try
    // Crear el JSON que queremos enviar
    jsonData.Add('title', 'Nuevo Post');
    jsonData.Add('body', 'Este es el contenido del post');
    jsonData.Add('userId', 1);
    
    jsonToSend := jsonData.AsJSON;
    
    // Configurar la cabecera para enviar JSON
    httpClient.AddHeader('Content-Type', 'application/json');
    httpClient.RequestBody := TRawByteStringStream.Create(jsonToSend);
    
    // Realizar la solicitud POST
    response := httpClient.Post('https://jsonplaceholder.typicode.com/posts');
    writeln('Respuesta de la API:', response);
    
  except
    on E: Exception do
      writeln('Error al hacer la solicitud POST: ', E.Message);
  end;
  jsonData.Free;
  httpClient.RequestBody.Free;
  httpClient.Free;
end.
```

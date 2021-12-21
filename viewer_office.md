# definition
for viewer office into pdf

# command
to convert into pdf using libre office
```
$cmd=" ".'"C:/Program Files/LibreOffice/program/soffice.exe"'.' --convert-to pdf --outdir "C:/tmpdata/" "'.$src.'" ';
```

to viewer cad cgm dwg to pdf
```
$c= new COM("CADConverter.CADConverterX");
$c->convert($src,$dest, "-c pdf -ps A4");
```

to viewer tiff to pdf
```
$cmd=" ".'"C:/Program Files/CoolUtils/CoolutilsConverterX/CoolutilsConverterX.exe"'.' "'.$src.'" '.'"'.$dest.'"'." -c pdf -ps A4";
```

to block download from idm
```
$filename = 'dummy.js';
header('Content-type: application/js');
header('Content-Disposition: inline; filename="' . $filename . '"');
header('Content-Transfer-Encoding: binary');
header('Content-Length: ' . filesize($dest));
header('Accept-Ranges: bytes');
```


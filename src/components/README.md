# Components

This folder contains the parts which are downloaded from third-party resources. A good
source of parts is (https://jlcpcb.com/parts). Parts from this website can be downloaded
and converted to KiCAD using the Python tool `JLC2KiCadLib`:

``` shell
poetry run JLC2KiCadLib C475134  -dir AliExpress -symbol_lib AliExpressSymbols
```

Above statement will:
- download the part `C475134`;
- into the folder `AliExpress`;
- into the symbol file `AliExpressSymbols`.

See for more information the [documentation](https://github.com/TousstNicolas/JLC2KiCad_lib)
of `JLC2KiCadLib`. 

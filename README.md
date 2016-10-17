# mgsv_path_hasher

Creates a filename hash used in fmdl/fv2 files in MGSVTPP (probably .dat files too).
See http://forum.xentax.com/viewtopic.php?p=121141#p121141 for more details on fmdl/fv2.

Put filenames you want to hash into 'input.txt', grab hashes from 'output.txt'.

Hashes are reversed by default so you can just copypaste the output and search for it 
using your favorite hex editor. Hashes are also truncated to last 12 bytes out of 16.
Options:
	'/r': re-reverse hashes;
	'/p': print hashes to console;
	'/h': supress any messages.

Based on atvaark's tool. https://dotnetfiddle.net/3RBp5V - online version without reversability.

Compiling:
 1. You will need .NET 4 and CityHash.dll - https://www.nuget.org/packages/CityHash.Net.Legacy/.
 2. Put CityHash.dll along with main.cs.
 3. Execute `C:\Windows\Microsoft.NET\Framework\v4.0.30319\csc.exe /r:CityHash.dll main.cs`
 4. Done.

Example:

|-         |-            |-   |
| ------------- |-------------:|-----:|
| Hex representation in fova |  | 5b ee d2 04 a5 a0 a2 84 |
| Full filepath | /Assets/tpp/item/ewr/Scenes/gog1_main0_def | 84 a2 a0 a5 04 d2 ee 5b |
| Trunkated filepath | tpp/item/ewr/Scenes/gog1_main0_def | 2 a0 a5 04 d2 ee 5b |

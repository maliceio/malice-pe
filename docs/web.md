# Create a PEscan micro-service

```bash
$ docker run -d -p 3993:3993 malice/pescan web

 * Serving Flask app "pescan" (lazy loading)
 * Environment: production
   WARNING: Do not use the development server in a production environment.
   Use a production WSGI server instead.
 * Debug mode: off
 * Running on http://0.0.0.0:3993/ (Press CTRL+C to quit)
```

## Now you can perform scans like so

```bash
$ http -f localhost:3993/scan malware@/path/to/evil/malware
```

> **NOTE:** I am using **httpie** to POST to the malice micro-service

```bash
HTTP/1.1 200 OK
Content-Length: 124
Content-Type: application/json; charset=UTF-8
Date: Sat, 21 Jan 2017 05:39:29 GMT

{
  "linker_version": "06.00",
  "compiletime": {
    "unix": 1164878434,
    "datetime": "2006-11-30 09:20:34"
  },
  "imports": [
    {
      "name": "GetStartupInfoA",
      "address": "0x406044"
    },
    {
      "name": "GetModuleHandleA",
      "address": "0x406048"
    },
    {
      "name": "CreatePipe",
      "address": "0x40604c"
    },
    {
      "name": "PeekNamedPipe",
      "address": "0x406050"
    },
    {
      "name": "ReadFile",
      "address": "0x406054"
    },
    {
      "name": "CreateProcessA",
      "address": "0x406058"
    },
    {
      "name": "MultiByteToWideChar",
      "address": "0x40605c"
    },
    {
      "name": "GlobalAlloc",
      "address": "0x406060"
    },
    {
      "name": "GlobalFree",
      "address": "0x406064"
    },
    {
      "name": "GetLocalTime",
      "address": "0x406068"
    },
    {
      "name": "RemoveDirectoryA",
      "address": "0x40606c"
    },
    {
      "name": "FindNextFileA",
      "address": "0x406070"
    },
    {
      "name": "FindFirstFileA",
      "address": "0x406074"
    },
    {
      "name": "GetFileTime",
      "address": "0x406078"
    },
    {
      "name": "SetFileTime",
      "address": "0x40607c"
    },
    {
      "name": "FindClose",
      "address": "0x406080"
    },
    {
      "name": "GetPriorityClass",
      "address": "0x406084"
    },
    {
      "name": "OpenProcess",
      "address": "0x406088"
    },
    {
      "name": "GetCurrentProcess",
      "address": "0x40608c"
    },
    {
      "name": "DuplicateHandle",
      "address": "0x406090"
    },
    {
      "name": "GetLastError",
      "address": "0x406094"
    },
    {
      "name": "LocalFree",
      "address": "0x406098"
    },
    {
      "name": "CreateToolhelp32Snapshot",
      "address": "0x40609c"
    },
    {
      "name": "Process32First",
      "address": "0x4060a0"
    },
    {
      "name": "Process32Next",
      "address": "0x4060a4"
    },
    {
      "name": "GetLogicalDriveStringsA",
      "address": "0x4060a8"
    },
    {
      "name": "GetDriveTypeA",
      "address": "0x4060ac"
    },
    {
      "name": "GetVolumeInformationA",
      "address": "0x4060b0"
    },
    {
      "name": "GetComputerNameA",
      "address": "0x4060b4"
    },
    {
      "name": "CreateFileA",
      "address": "0x4060b8"
    },
    {
      "name": "GetFileSize",
      "address": "0x4060bc"
    },
    {
      "name": "WriteFile",
      "address": "0x4060c0"
    },
    {
      "name": "LoadLibraryA",
      "address": "0x4060c4"
    },
    {
      "name": "GetProcAddress",
      "address": "0x4060c8"
    },
    {
      "name": "FreeLibrary",
      "address": "0x4060cc"
    },
    {
      "name": "GetVersionExA",
      "address": "0x4060d0"
    },
    {
      "name": "GetSystemDefaultLangID",
      "address": "0x4060d4"
    },
    {
      "name": "OpenMutexA",
      "address": "0x4060d8"
    },
    {
      "name": "CreateMutexA",
      "address": "0x4060dc"
    },
    {
      "name": "CloseHandle",
      "address": "0x4060e0"
    },
    {
      "name": "lstrcmpiA",
      "address": "0x4060e4"
    },
    {
      "name": "ExitProcess",
      "address": "0x4060e8"
    },
    {
      "name": "SetEvent",
      "address": "0x4060ec"
    },
    {
      "name": "WaitForSingleObject",
      "address": "0x4060f0"
    },
    {
      "name": "Sleep",
      "address": "0x4060f4"
    },
    {
      "name": "DeleteFileA",
      "address": "0x4060f8"
    },
    {
      "name": "CopyFileA",
      "address": "0x4060fc"
    },
    {
      "name": "GetWindowsDirectoryA",
      "address": "0x406100"
    },
    {
      "name": "GetModuleFileNameA",
      "address": "0x406104"
    },
    {
      "name": "CreateDirectoryA",
      "address": "0x406108"
    },
    {
      "name": "GetFileAttributesA",
      "address": "0x40610c"
    },
    {
      "name": "SetFileAttributesA",
      "address": "0x406110"
    },
    {
      "name": "CreateEventA",
      "address": "0x406114"
    },
    {
      "name": "CreateThread",
      "address": "0x406118"
    },
    {
      "name": "RegCloseKey",
      "address": "0x406000"
    },
    {
      "name": "RegSetValueExA",
      "address": "0x406004"
    },
    {
      "name": "RegQueryValueExA",
      "address": "0x406008"
    },
    {
      "name": "RegCreateKeyExA",
      "address": "0x40600c"
    },
    {
      "name": "RegDeleteValueA",
      "address": "0x406010"
    },
    {
      "name": "RegOpenKeyExA",
      "address": "0x406014"
    },
    {
      "name": "SetSecurityInfo",
      "address": "0x406018"
    },
    {
      "name": "SetEntriesInAclA",
      "address": "0x40601c"
    },
    {
      "name": "AdjustTokenPrivileges",
      "address": "0x406020"
    },
    {
      "name": "LookupPrivilegeValueA",
      "address": "0x406024"
    },
    {
      "name": "GetTokenInformation",
      "address": "0x406028"
    },
    {
      "name": "OpenProcessToken",
      "address": "0x40602c"
    },
    {
      "name": "GetUserNameA",
      "address": "0x406030"
    },
    {
      "name": "LookupAccountSidA",
      "address": "0x406034"
    },
    {
      "name": "RegEnumKeyExA",
      "address": "0x406038"
    },
    {
      "name": "RegEnumValueA",
      "address": "0x40603c"
    },
    {
      "name": "WNetCloseEnum",
      "address": "0x406120"
    },
    {
      "name": "WNetOpenEnumA",
      "address": "0x406124"
    },
    {
      "name": "WNetEnumResourceA",
      "address": "0x406128"
    },
    {
      "name": "_except_handler3",
      "address": "0x406130"
    },
    {
      "name": "__set_app_type",
      "address": "0x406134"
    },
    {
      "name": "__p__fmode",
      "address": "0x406138"
    },
    {
      "name": "__p__commode",
      "address": "0x40613c"
    },
    {
      "name": "_adjust_fdiv",
      "address": "0x406140"
    },
    {
      "name": "__setusermatherr",
      "address": "0x406144"
    },
    {
      "name": "_initterm",
      "address": "0x406148"
    },
    {
      "name": "__getmainargs",
      "address": "0x40614c"
    },
    {
      "name": "_acmdln",
      "address": "0x406150"
    },
    {
      "name": "exit",
      "address": "0x406154"
    },
    {
      "name": "_XcptFilter",
      "address": "0x406158"
    },
    {
      "name": "_exit",
      "address": "0x40615c"
    },
    {
      "name": "swprintf",
      "address": "0x406160"
    },
    {
      "name": "fwrite",
      "address": "0x406164"
    },
    {
      "name": "fopen",
      "address": "0x406168"
    },
    {
      "name": "fseek",
      "address": "0x40616c"
    },
    {
      "name": "fread",
      "address": "0x406170"
    },
    {
      "name": "fclose",
      "address": "0x406174"
    },
    {
      "name": "_strnicmp",
      "address": "0x406178"
    },
    {
      "name": "strcmp",
      "address": "0x40617c"
    },
    {
      "name": "sprintf",
      "address": "0x406180"
    },
    {
      "name": "memcpy",
      "address": "0x406184"
    },
    {
      "name": "strstr",
      "address": "0x406188"
    },
    {
      "name": "strchr",
      "address": "0x40618c"
    },
    {
      "name": "atoi",
      "address": "0x406190"
    },
    {
      "name": "memset",
      "address": "0x406194"
    },
    {
      "name": "strlen",
      "address": "0x406198"
    },
    {
      "name": "strrchr",
      "address": "0x40619c"
    },
    {
      "name": "time",
      "address": "0x4061a0"
    },
    {
      "name": "srand",
      "address": "0x4061a4"
    },
    {
      "name": "rand",
      "address": "0x4061a8"
    },
    {
      "name": "strcpy",
      "address": "0x4061ac"
    },
    {
      "name": "strcat",
      "address": "0x4061b0"
    },
    {
      "name": "malloc",
      "address": "0x4061b4"
    },
    {
      "name": "_EH_prolog",
      "address": "0x4061b8"
    },
    {
      "name": "__CxxFrameHandler",
      "address": "0x4061bc"
    },
    {
      "name": "rename",
      "address": "0x4061c0"
    },
    {
      "name": "_controlfp",
      "address": "0x4061c4"
    },
    {
      "name": "free",
      "address": "0x4061c8"
    },
    {
      "name": "_itoa",
      "address": "0x4061cc"
    },
    {
      "name": "SHDeleteKeyA",
      "address": "0x4061d4"
    },
    {
      "name": "gethostname",
      "address": "0x4061dc"
    },
    {
      "name": "gethostbyname",
      "address": "0x4061e0"
    },
    {
      "name": "WSAGetLastError",
      "address": "0x4061e4"
    },
    {
      "name": "inet_ntoa",
      "address": "0x4061e8"
    },
    {
      "name": "inet_addr",
      "address": "0x4061ec"
    },
    {
      "name": "socket",
      "address": "0x4061f0"
    },
    {
      "name": "htons",
      "address": "0x4061f4"
    },
    {
      "name": "connect",
      "address": "0x4061f8"
    },
    {
      "name": "select",
      "address": "0x4061fc"
    },
    {
      "name": "send",
      "address": "0x406200"
    },
    {
      "name": "closesocket",
      "address": "0x406204"
    },
    {
      "name": "recv",
      "address": "0x406208"
    },
    {
      "name": "WSAStartup",
      "address": "0x40620c"
    },
    {
      "name": "WSACleanup",
      "address": "0x406210"
    },
    {
      "name": "ioctlsocket",
      "address": "0x406214"
    }
  ],
  "resource_versioninfo": {
    "legalcopyright": "(C) Microsoft Corporation. All rights reserved.",
    "internalname": "iexplore",
    "fileversion": "6.00.2900.2180 (xpsp_sp2_rtm.040803-2158)",
    "companyname": "Microsoft Corporation",
    "productname": "Microsoft(R) Windows(R) Operating System",
    "productversion": "6.00.2900.2180",
    "original_filename": "IEXPLORE.EXE",
    "file_description": "Internet Explorer"
  },
  "rich_header_info": [
    {
      "tool_id": 12,
      "version": 7291,
      "times used": 1
    },
    {
      "tool_id": 14,
      "version": 7299,
      "times used": 2
    },
    {
      "tool_id": 10,
      "version": 8168,
      "times used": 11
    },
    {
      "tool_id": 4,
      "version": 8168,
      "times used": 2
    },
    {
      "tool_id": 0,
      "version": 0,
      "times used": 3
    },
    {
      "tool_id": 1,
      "version": 0,
      "times used": 151
    },
    {
      "tool_id": 19,
      "version": 8034,
      "times used": 9
    },
    {
      "tool_id": 11,
      "version": 8168,
      "times used": 2
    },
    {
      "tool_id": 6,
      "version": 1720,
      "times used": 1
    }
  ],
  "os_version": "04.00",
  "is_packed": false,
  "entrypoint": "0x5a46",
  "sections": [
    {
      "raw_data_size": 20480,
      "name": ".text",
      "rva": "0x1000",
      "pointer_to_raw_data": 4096,
      "entropy": 5.988944574755928,
      "virtual_size": "0x4bfe"
    },
    {
      "raw_data_size": 4096,
      "name": ".rdata",
      "rva": "0x6000",
      "pointer_to_raw_data": 24576,
      "entropy": 3.291179369026711,
      "virtual_size": "0xc44"
    },
    {
      "raw_data_size": 4096,
      "name": ".data",
      "rva": "0x7000",
      "pointer_to_raw_data": 28672,
      "entropy": 4.04448531075933,
      "virtual_size": "0x17b0"
    },
    {
      "raw_data_size": 8192,
      "name": ".rsrc",
      "rva": "0x9000",
      "pointer_to_raw_data": 32768,
      "entropy": 4.49716326553469,
      "virtual_size": "0x15d0"
    }
  ],
  "resources": [
    {
      "language_desc": "Chinese-People's Republic of China",
      "sublanguage": "SUBLANG_CHINESE_SIMPLIFIED",
      "name": "RT_ICON",
      "language": "LANG_CHINESE",
      "offset": "0x90f0",
      "size": "0x10a8",
      "type": "data",
      "id": 1,
      "md5": "14bf7c82dcfb7e41243f5b87d0c79538"
    },
    {
      "language_desc": "Chinese-People's Republic of China",
      "sublanguage": "SUBLANG_CHINESE_SIMPLIFIED",
      "name": "RT_GROUP_ICON",
      "language": "LANG_CHINESE",
      "offset": "0xa198",
      "size": "0x14",
      "type": "data",
      "id": 2,
      "md5": "3c68f77c35c26ff079a1c410ee44fa62"
    },
    {
      "language_desc": "Chinese-People's Republic of China",
      "sublanguage": "SUBLANG_CHINESE_SIMPLIFIED",
      "name": "RT_VERSION",
      "language": "LANG_CHINESE",
      "offset": "0xa1b0",
      "size": "0x41c",
      "type": "data",
      "id": 3,
      "md5": "9a12ece86a71c3499df0fb0ebe6ea33e"
    }
  ],
  "peid": [
    "Armadillo v1.71",
    "Microsoft Visual C++ v5.0/v6.0 (MFC)",
    "Microsoft Visual C++"
  ],
  "calculated_file_size": 42448,
  "imphash": "a2cee99c7e42d671d47e3fb71c71bda4",
  "number_of_sections": 4,
  "pehash": "884bf0684addc269d641efb74e0fcb88267211da",
  "machine_type": "0x14c (IMAGE_FILE_MACHINE_I386)",
  "image_base": 4194304,
  "language": "C",
  "data_directories": [
    {
      "virtual_address": "0x6288",
      "name": "IMPORT",
      "size": 140
    },
    {
      "virtual_address": "0x9000",
      "name": "RESOURCE",
      "size": 5584
    }
  ],
  "size_of_image": 45056,
  "signature": {
    "heuristic": "No file signature data found"
  }
}
```

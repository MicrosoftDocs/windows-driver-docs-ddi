---
UID: NS:winsplp._SPLCLIENT_INFO_1
title: "_SPLCLIENT_INFO_1"
author: windows-driver-content
description: The SPLCLIENT_INFO_1 structure is used as input to the GenerateCopyFilePaths function that is exported by Point and Print DLLs.
old-location: print\splclient_info_1.htm
old-project: print
ms.assetid: a9659f77-e84b-471a-a778-a4628d89ce19
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: SPLCLIENT_INFO_1, LPSPLCLIENT_INFO_1, PSPLCLIENT_INFO_1, winsplp/LPSPLCLIENT_INFO_1, PSPLCLIENT_INFO_1 structure pointer [Print Devices], print.splclient_info_1, *LPSPLCLIENT_INFO_1, winsplp/SPLCLIENT_INFO_1, *PSPLCLIENT_INFO_1, LPSPLCLIENT_INFO_1 structure pointer [Print Devices], _SPLCLIENT_INFO_1, poprfnc_45237404-33da-4fb0-9405-05c930c5445b.xml, winsplp/PSPLCLIENT_INFO_1, SPLCLIENT_INFO_1 structure [Print Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	winsplp.h
apiname:
-	SPLCLIENT_INFO_1
product: Windows
targetos: Windows
req.typenames: "*PSPLCLIENT_INFO_1, SPLCLIENT_INFO_1, *LPSPLCLIENT_INFO_1"
req.product: Windows 10 or later.
---

# _SPLCLIENT_INFO_1 structure


## -description


The SPLCLIENT_INFO_1 structure is used as input to the <a href="..\winsplp\nf-winsplp-generatecopyfilepaths.md">GenerateCopyFilePaths</a> function that is exported by <a href="https://msdn.microsoft.com/7ead940e-8426-4756-890f-f3607dc1f9ca">Point and Print DLLs</a>.


## -syntax


````
typedef struct _SPLCLIENT_INFO_1 {
  DWORD  dwSize;
  LPWSTR pMachineName;
  LPWSTR pUserName;
  DWORD  dwBuildNum;
  DWORD  dwMajorVersion;
  DWORD  dwMinorVersion;
  WORD   wProcessorArchitecture;
} SPLCLIENT_INFO_1, *PSPLCLIENT_INFO_1, *LPSPLCLIENT_INFO_1;
````


## -struct-fields




### -field dwSize

Size of the SPLCLIENT_INFO_1 structure.


### -field pMachineName

Not used.


### -field pUserName

Not used.


### -field dwBuildNum

The build number of the version of the NT-based operating system running on the client, as returned by the Microsoft Window SDK <b>GetVersionEx</b> function.


### -field dwMajorVersion

The major version number of the NT-based operating system print spooler running on the client.


### -field dwMinorVersion

The minor version number of the NT-based operating system print spooler running on the client.


### -field wProcessorArchitecture

The client's processor architecture, as returned by the Window SDK <b>GetSystemInfo</b> function.


## -remarks


Values for all structure members are supplied by the print spooler before the spooler calls <a href="..\winsplp\nf-winsplp-generatecopyfilepaths.md">GenerateCopyFilePaths</a>.



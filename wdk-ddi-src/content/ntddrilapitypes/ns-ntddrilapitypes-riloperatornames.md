---
UID: NS:ntddrilapitypes.RILOPERATORNAMES
title: RILOPERATORNAMES
author: windows-driver-content
description: This structure represents the RILOPERATORNAMES.
old-location: netvista\riloperatornames.htm
old-project: netvista
ms.assetid: 2813c28c-e964-44ee-9995-15aa563c43d0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: rilapitypes/RILOPERATORNAMES, netvista.riloperatornames, RILOPERATORNAMES, *LPRILOPERATORNAMES, RILOPERATORNAMES structure [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
req.include-header: Rilapitypes.h, Ntddrilapitypes.h
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
-	rilapitypes.h
apiname:
-	RILOPERATORNAMES
product: Windows
targetos: Windows
req.typenames: "*LPRILOPERATORNAMES, RILOPERATORNAMES"
---

# RILOPERATORNAMES structure


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents the RILOPERATORNAMES.


## -syntax


````
struct RILOPERATORNAMES {
  DWORD cbSize;
  DWORD dwParams;
  DWORD dwSystemType;
  WCHAR wszLongName[MAXLENGTH_OPERATOR_LONG];
  WCHAR wszShortName[MAXLENGTH_OPERATOR_SHORT];
  WCHAR wszNumName[MAXLENGTH_OPERATOR_NUMERIC];
  WCHAR wszCountryCode[MAXLENGTH_OPERATOR_COUNTRY_CODE];
};
````


## -struct-fields




### -field cbSize

The size of the structure in bytes.


### -field dwParams

A bitwise combination of <a href="..\ntddrilapitypes\ne-ntddrilapitypes-riloperatornamesparammask.md">RILOPERATORNAMESPARAMMASK</a> enumeration values that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set.


### -field dwSystemType

Must specify one and only one system type.


### -field wszLongName


### -field wszShortName


### -field wszNumName


### -field wszCountryCode

Mobile country code


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILOPERATORNAMES structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


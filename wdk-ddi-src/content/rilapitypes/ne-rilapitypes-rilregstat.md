---
UID: NE:rilapitypes.RILREGSTAT
title: RILREGSTAT
author: windows-driver-content
description: This enumeration describes the RILREGSTAT.
old-location: netvista\rilregstat.htm
old-project: netvista
ms.assetid: 53c72dbb-cf8d-4683-a440-985669265a52
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILREGSTAT enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_REGSTAT_HOME, RIL_REGSTAT_DENIED, RILREGSTAT, rilapitypes/RIL_REGSTAT_DENIED, netvista.rilregstat, RIL_REGSTAT_UNREGISTERED, RIL_REGSTAT_ROAMING_INTL, RIL_REGSTAT_HOME, rilapitypes/RIL_REGSTAT_UNKNOWN, RIL_REGSTAT_ATTEMPTING, rilapitypes/RIL_REGSTAT_ROAMING, RIL_REGSTAT_UNKNOWN, rilapitypes/RIL_REGSTAT_UNREGISTERED, RIL_REGSTAT_ROAMING, rilapitypes/RIL_REGSTAT_ROAMING_INTL, rilapitypes/RILREGSTAT, rilapitypes/RIL_REGSTAT_ATTEMPTING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
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
req.lib: NtosKrnl.exe
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
-	RILREGSTAT
product: Windows
targetos: Windows
req.typenames: RILREGSTAT
req.product: Windows 10 or later.
---

# RILREGSTAT enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILREGSTAT.


## -syntax


````
enum RILREGSTAT  {
  RIL_REGSTAT_UNKNOWN       = 0x00000000, 
  RIL_REGSTAT_UNREGISTERED  = 0x00000001, 
  RIL_REGSTAT_HOME          = 0x00000002, 
  RIL_REGSTAT_ATTEMPTING    = 0x00000003, 
  RIL_REGSTAT_DENIED        = 0x00000004, 
  RIL_REGSTAT_ROAMING       = 0x00000005, 
  RIL_REGSTAT_ROAMING_INTL  = 0x00000006 

};
````


## -enum-fields




### -field RIL_REGSTAT_UNKNOWN



### -field RIL_REGSTAT_UNREGISTERED



### -field RIL_REGSTAT_HOME



### -field RIL_REGSTAT_ATTEMPTING



### -field RIL_REGSTAT_DENIED



### -field RIL_REGSTAT_ROAMING



### -field RIL_REGSTAT_ROAMING_DOMESTIC



### -field RIL_REGSTAT_MAX




#### - RIL_REGSTAT_ROAMING_INTL



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILREGSTAT enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


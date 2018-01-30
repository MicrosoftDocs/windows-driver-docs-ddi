---
UID: NE:rilapitypes.RILUICCFILELOCKSTATUSPARAMMASK
title: RILUICCFILELOCKSTATUSPARAMMASK
author: windows-driver-content
description: This enumeration describes the RILUICCFILELOCKSTATUSPARAMMASK.
old-location: netvista\riluiccfilelockstatusparammask.htm
old-project: netvista
ms.assetid: 341e11bb-957b-4745-9892-f1274ff97f44
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RIL_PARAM_UFLS_ALL, RIL_PARAM_UFLS_PINREFERENCE, rilapitypes/RIL_PARAM_UFLS_PINREFERENCE, rilapitypes/RIL_PARAM_UFLS_ACCESSCONDITION, RIL_PARAM_UFLS_ACCESSCONDITION, rilapitypes/RILUICCFILELOCKSTATUSPARAMMASK, RIL_PARAM_UFLS_ALL, RILUICCFILELOCKSTATUSPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RILUICCFILELOCKSTATUSPARAMMASK, netvista.riluiccfilelockstatusparammask
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
-	RILUICCFILELOCKSTATUSPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILUICCFILELOCKSTATUSPARAMMASK
req.product: Windows 10 or later.
---

# RILUICCFILELOCKSTATUSPARAMMASK enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILUICCFILELOCKSTATUSPARAMMASK.


## -syntax


````
enum RILUICCFILELOCKSTATUSPARAMMASK {
  RIL_PARAM_UFLS_ACCESSCONDITION  = 0x00000001, 
  RIL_PARAM_UFLS_PINREFERENCE     = 0x00000002, 
  RIL_PARAM_UFLS_ALL              = 0x00000003 

};
````


## -enum-fields




### -field RIL_PARAM_UFLS_ACCESSCONDITION



### -field RIL_PARAM_UFLS_PINREFERENCE



### -field RIL_PARAM_UFLS_ALL



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILUICCFILELOCKSTATUSPARAMMASK enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


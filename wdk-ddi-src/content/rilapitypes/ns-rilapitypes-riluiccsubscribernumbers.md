---
UID: NS:rilapitypes.RILUICCSUBSCRIBERNUMBERS
title: RILUICCSUBSCRIBERNUMBERS
author: windows-driver-content
description: This structure represents RILUICCSUBSCRIBERNUMBERS.
old-location: netvista\riluiccsubscribernumbers.htm
old-project: netvista
ms.assetid: 7c9f7c52-edb3-48cd-b532-0e100692fee4
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.riluiccsubscribernumbers, rilapitypes/RILUMTSMRL, RILUICCSUBSCRIBERNUMBERS structure [Network Drivers Starting with Windows Vista], *LPRILUICCSUBSCRIBERNUMBERS, RILUICCSUBSCRIBERNUMBERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	RILUMTSMRL
product: Windows
targetos: Windows
req.typenames: "*LPRILUICCSUBSCRIBERNUMBERS, RILUICCSUBSCRIBERNUMBERS"
req.product: Windows 10 or later.
---

# RILUICCSUBSCRIBERNUMBERS structure


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents RILUICCSUBSCRIBERNUMBERS.


## -syntax


````
struct RILUMTSMRL {
  DWORD             cbSize;
  DWORD             dwNumSubscribers;
  RILSUBSCRIBERINFO rsiInfo[1];
};
````


## -struct-fields




### -field cbSize

The size of the structure in bytes.


### -field dwNumSubscribers

The number of subscribers.


### -field rsiInfo

Array of <a href="..\rilapitypes\ns-rilapitypes-rilsubscriberinfo.md">RILSUBSCRIBERINFO</a>, each of which specifies a phone number assigned to the user as defined below. Although statically declared as a one-element array, the actual length is dwNumSubscribers.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILUICCSUBSCRIBERNUMBERS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


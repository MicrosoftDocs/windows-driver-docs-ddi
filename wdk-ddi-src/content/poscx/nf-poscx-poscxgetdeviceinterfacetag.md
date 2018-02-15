---
UID: NF:poscx.PosCxGetDeviceInterfaceTag
title: PosCxGetDeviceInterfaceTag function
author: windows-driver-content
description: PosCxGetDeviceInterfaceTag returns the device interface tag that is set in PosCxOpen.
old-location: pos\poscxgetdeviceinterfacetag.htm
old-project: pos
ms.assetid: CF54D922-8EEE-41CE-8CFC-0628756117BE
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PosCxGetDeviceInterfaceTag function, poscx/PosCxGetDeviceInterfaceTag, PosCxGetDeviceInterfaceTag, pos.poscxgetdeviceinterfacetag
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: poscx.h
req.include-header: Poscx.h
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
-	poscx.h
apiname:
-	PosCxGetDeviceInterfaceTag
product: Windows
targetos: Windows
req.typenames: POS_CX_EVENT_PRIORITY
req.product: Windows 10 or later.
---

# PosCxGetDeviceInterfaceTag function


## -description


PosCxGetDeviceInterfaceTag returns the device interface tag that is set in <a href="..\poscx\nf-poscx-poscxopen.md">PosCxOpen</a>.


## -syntax


````
ULONG PosCxGetDeviceInterfaceTag(
  _In_ WDFFILEOBJECT fileObject
);
````


## -parameters




### -param fileObject [in]

      A handle to a framework file object that identifies the caller, usually acquired with <a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetfileobject.md">WdfRequestGetFileObject</a>.


## -returns



      The device interface tag value.




## -see-also

<a href="..\poscx\nf-poscx-poscxopen.md">PosCxOpen</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [pos\pos]:%20PosCxGetDeviceInterfaceTag function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


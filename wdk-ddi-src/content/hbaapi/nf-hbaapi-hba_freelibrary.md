---
UID: NF:hbaapi.HBA_FreeLibrary
title: HBA_FreeLibrary function
author: windows-driver-content
description: The HBA_FreeLibrary routine releases system resources associated with fibre channel HBA library.
old-location: storage\hba_freelibrary.htm
old-project: storage
ms.assetid: 513cdedc-2ecd-4b02-a85b-5abd9c0c7fcd
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: hbaapi/HBA_FreeLibrary, storage.hba_freelibrary, HBA_FreeLibrary routine [Storage Devices], fibreHBA_rtns_ae252017-7aa2-4d15-a387-26ec34cc964c.xml, HBA_FreeLibrary
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Desktop
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
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Hbaapi.dll
apiname:
-	HBA_FreeLibrary
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---

# HBA_FreeLibrary function


## -description


The <b>HBA_FreeLibrary</b> routine releases system resources associated with fibre channel HBA library.


## -syntax


````
HBA_STATUS HBA_API HBA_FreeLibrary(void);
````


## -parameters






## -returns



The <b>HBA_FreeLibrary</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_FreeLibrary routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


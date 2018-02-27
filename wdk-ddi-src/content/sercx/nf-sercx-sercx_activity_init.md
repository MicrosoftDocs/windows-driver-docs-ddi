---
UID: NF:sercx.SERCX_ACTIVITY_INIT
title: SERCX_ACTIVITY_INIT function
author: windows-driver-content
description: The SERCX_ACTIVITY_INIT function initializes a SERCX_ACTIVITY structure.
old-location: serports\sercx_activity_init.htm
old-project: serports
ms.assetid: 211A3DBB-96B8-4DB5-BB50-FAB7500D999F
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 1/SERCX_ACTIVITY_INIT, SERCX_ACTIVITY_INIT, SERCX_ACTIVITY_INIT function [Serial Ports], serports.sercx_activity_init
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: Any IRQL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	1.0\Sercx.h
apiname:
-	SERCX_ACTIVITY_INIT
product: Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---

# SERCX_ACTIVITY_INIT function


## -description


The <b>SERCX_ACTIVITY_INIT</b> function initializes a <a href="..\sercx\ns-sercx-_sercx_activity.md">SERCX_ACTIVITY</a> structure.


## -syntax


````
VOID SERCX_ACTIVITY_INIT(
  _Out_ SERCX_ACTIVITY *Activity
);
````


## -parameters




### -param Activity [out]

A pointer to the <b>SERCX_ACTIVITY</b> structure that is to be initialized.


## -returns



None.




## -see-also

<a href="..\sercx\ns-sercx-_sercx_activity.md">SERCX_ACTIVITY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SERCX_ACTIVITY_INIT function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


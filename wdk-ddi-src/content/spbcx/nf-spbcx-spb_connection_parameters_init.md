---
UID: NF:spbcx.SPB_CONNECTION_PARAMETERS_INIT
title: SPB_CONNECTION_PARAMETERS_INIT function
author: windows-driver-content
description: The SPB_CONNECTION_PARAMETERS_INIT function initializes an SPB_CONNECTION_PARAMETERS structure.
old-location: spb\spb_connection_parameters_init.htm
old-project: SPB
ms.assetid: 0E23690B-4AE1-42F1-A53F-FE9A4697DBF2
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: spbcx/SPB_CONNECTION_PARAMETERS_INIT, SPB.spb_connection_parameters_init, SPB_CONNECTION_PARAMETERS_INIT function [Buses], SPB_CONNECTION_PARAMETERS_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: spbcx.h
req.include-header: 
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: Any IRQL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Spbcx.h
apiname:
-	SPB_CONNECTION_PARAMETERS_INIT
product: Windows
targetos: Windows
req.typenames: SPB_REQUEST_TYPE, *PSPB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# SPB_CONNECTION_PARAMETERS_INIT function


## -description


The <b>SPB_CONNECTION_PARAMETERS_INIT</b> function initializes an  <a href="https://msdn.microsoft.com/library/windows/hardware/hh406204">SPB_CONNECTION_PARAMETERS</a> structure.


## -syntax


````
VOID SPB_CONNECTION_PARAMETERS_INIT(
  _Out_ SPB_CONNECTION_PARAMETERS *Parameters
);
````


## -parameters




### -param Parameters [out]

A pointer to the <b>SPB_CONNECTION_PARAMETERS</b> structure that is to be initialized.


## -returns



None.




## -remarks



Your SPB controller driver must use this function to initialize an <b>SPB_CONNECTION_PARAMETERS</b> structure before passing this structure as an output parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450926">SpbTargetGetConnectionParameters</a> method. This method writes the connection parameters for a target device on the bus to this structure.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450926">SpbTargetGetConnectionParameters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406204">SPB_CONNECTION_PARAMETERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SPB\buses]:%20SPB_CONNECTION_PARAMETERS_INIT function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


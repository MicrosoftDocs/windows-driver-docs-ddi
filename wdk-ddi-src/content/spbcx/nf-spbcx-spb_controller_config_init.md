---
UID: NF:spbcx.SPB_CONTROLLER_CONFIG_INIT
title: SPB_CONTROLLER_CONFIG_INIT function
author: windows-driver-content
description: The SPB_CONTROLLER_CONFIG_INIT function initializes an SPB_CONTROLLER_CONFIG structure.
old-location: spb\spb_controller_config_init.htm
old-project: SPB
ms.assetid: 78D46903-A13D-4BC2-803F-E1656A43E865
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: SPB_CONTROLLER_CONFIG_INIT function [Buses], spbcx/SPB_CONTROLLER_CONFIG_INIT, SPB.spb_controller_config_init, SPB_CONTROLLER_CONFIG_INIT
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
-	SPB_CONTROLLER_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: "*PSPB_REQUEST_TYPE, SPB_REQUEST_TYPE"
req.product: Windows 10 or later.
---

# SPB_CONTROLLER_CONFIG_INIT function


## -description


The <b>SPB_CONTROLLER_CONFIG_INIT</b> function initializes an <a href="https://msdn.microsoft.com/library/windows/hardware/hh406206">SPB_CONTROLLER_CONFIG</a> structure.


## -syntax


````
VOID SPB_CONTROLLER_CONFIG_INIT(
  _Out_ SPB_CONTROLLER_CONFIG *Config
);
````


## -parameters




### -param Config [out]

A pointer to the <b>SPB_CONTROLLER_CONFIG</b> structure that is to be initialized.


## -returns



None.




## -remarks



Your SPB controller driver must use this function to initialize an <b>SPB_CONTROLLER_CONFIG</b> structure before passing this structure as an input parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450919">SpbDeviceInitialize</a> method. This method completes the initialization of the SPB framework extension (SpbCx).




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406206">SPB_CONTROLLER_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450919">SpbDeviceInitialize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SPB\buses]:%20SPB_CONTROLLER_CONFIG_INIT function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


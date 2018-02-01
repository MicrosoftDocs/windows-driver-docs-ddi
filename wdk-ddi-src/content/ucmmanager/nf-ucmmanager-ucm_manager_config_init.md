---
UID: NF:ucmmanager.UCM_MANAGER_CONFIG_INIT
title: UCM_MANAGER_CONFIG_INIT function
author: windows-driver-content
description: Initializes a UCM_MANAGER_CONFIG structure.
old-location: buses\ucm_manager_config_init.htm
old-project: usbref
ms.assetid: 5247D5F0-8422-48C1-81AF-98C8A3537FAD
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: UCM_MANAGER_CONFIG_INIT function [Buses], UCM_MANAGER_CONFIG_INIT, ucmmanager/UCM_MANAGER_CONFIG_INIT, buses.ucm_manager_config_init
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucmmanager.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
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
-	Ucmmanager.h
apiname:
-	UCM_MANAGER_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: "*PPORT_DATA_1, PORT_DATA_1"
req.product: Windows 10 or later.
---

# UCM_MANAGER_CONFIG_INIT function


## -description


Initializes a <a href="..\ucmmanager\ns-ucmmanager-_ucm_manager_config.md">UCM_MANAGER_CONFIG</a> structure.


## -syntax


````
FORCEINLINE void UCM_MANAGER_CONFIG_INIT(
  _Out_ PUCM_MANAGER_CONFIG  Config
);
````


## -parameters




### -param Config [out]

Pointer to a caller-allocated <a href="..\ucmmanager\ns-ucmmanager-_ucm_manager_config.md">UCM_MANAGER_CONFIG</a> structure to initialize.


## -returns


This function does not return a value.



## -see-also

<a href="..\ucmmanager\ns-ucmmanager-_ucm_manager_config.md">UCM_MANAGER_CONFIG</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCM_MANAGER_CONFIG_INIT function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


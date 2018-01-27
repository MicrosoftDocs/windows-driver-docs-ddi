---
UID: NC:61883.PBUS_RESET_ROUTINE
title: PBUS_RESET_ROUTINE
author: windows-driver-content
description: This is a caller-supplied function to be called by the protocol driver when the 1394 bus is reset.
old-location: ieee\pbus_reset_routine.htm
old-project: IEEE
ms.assetid: 99555765-A58F-45A1-B146-3742C390E666
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IEEE.pbus_reset_routine, BusResetRoutine callback function [Buses], BusResetRoutine, PBUS_RESET_ROUTINE, PBUS_RESET_ROUTINE, 61883/BusResetRoutine, BusResetRoutine callback function [Buses], BusResetRoutine
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: 61883.h
req.include-header: 
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
-	UserDefined
apilocation: 
-	61883.h
apiname: 
-	BusResetRoutine
product: Windows
targetos: Windows
req.typenames: *PTOPOLOGY_MAP, TOPOLOGY_MAP
---

# PBUS_RESET_ROUTINE callback


## -description


This is a caller-supplied function to be called by the protocol driver when the 1394 bus is reset.


## -prototype


````
PBUS_RESET_ROUTINE BusResetRoutine;

void BusResetRoutine(
  _In_ PVOID                Context,
  _In_ PBUS_GENERATION_NODE BusResetInfo
)
{ ... }

typedef PBUS_RESET_ROUTINE BusResetRoutine;
````


## -parameters




### -param Context [in]

Pointer to the context supplied by the caller at the <b>Context</b> member of the input BUS_RESET_NOTIFY structure. 


### -param BusResetInfo [in]

The bus reset information. 


## -returns


This callback does not return a value.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20PBUS_RESET_ROUTINE callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


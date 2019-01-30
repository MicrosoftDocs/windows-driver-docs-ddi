---
UID: NE:portabledevice.tagWPD_OPERATION_STATES
title: tagWPD_OPERATION_STATES (portabledevice.h)
description: The WPD_OPERATION_STATES enumeration values describe the current state of an operation in progress.
old-location: wpddk\wpd_operation_states.htm
tech.root: wpd_dk
ms.assetid: 989bb572-b974-4fee-900e-81f42da70e57
ms.date: 02/15/2018
ms.keywords: WPD_OPERATION_STATES, WPD_OPERATION_STATES enumeration, WPD_OPERATION_STATE_ABORTED, WPD_OPERATION_STATE_CANCELLED, WPD_OPERATION_STATE_FINISHED, WPD_OPERATION_STATE_PAUSED, WPD_OPERATION_STATE_RUNNING, WPD_OPERATION_STATE_STARTED, WPD_OPERATION_STATE_UNSPECIFIED, portabledevice/WPD_OPERATION_STATES, portabledevice/WPD_OPERATION_STATE_ABORTED, portabledevice/WPD_OPERATION_STATE_CANCELLED, portabledevice/WPD_OPERATION_STATE_FINISHED, portabledevice/WPD_OPERATION_STATE_PAUSED, portabledevice/WPD_OPERATION_STATE_RUNNING, portabledevice/WPD_OPERATION_STATE_STARTED, portabledevice/WPD_OPERATION_STATE_UNSPECIFIED, tagWPD_OPERATION_STATES, wpddk.wpd_operation_states
ms.topic: enum
req.header: portabledevice.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	PortableDevice.h
api_name:
-	WPD_OPERATION_STATES
product:
-	Windows
targetos: Windows
req.typenames: WPD_OPERATION_STATES
ms.custom: RS5
---

# tagWPD_OPERATION_STATES enumeration


## -description



The <b>WPD_OPERATION_STATES</b> enumeration values describe the current state of an operation in progress.




## -enum-fields




### -field WPD_OPERATION_STATE_UNSPECIFIED

The current operation is in an unspecified state (not set) and unknown.


### -field WPD_OPERATION_STATE_STARTED

The operation is started.


### -field WPD_OPERATION_STATE_RUNNING

The operation is running.


### -field WPD_OPERATION_STATE_PAUSED

The operation is paused.


### -field WPD_OPERATION_STATE_CANCELLED

The operation is canceled.


### -field WPD_OPERATION_STATE_FINISHED

The operation is finished.


### -field WPD_OPERATION_STATE_ABORTED

The operation is aborted.


## -remarks



These values are received in an application-defined callback.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff597672">Structures and Enumeration Types</a>
 

 


---
UID: NC:poscx.EVT_POS_CX_DEVICE_OWNERSHIP_CHANGE
title: EVT_POS_CX_DEVICE_OWNERSHIP_CHANGE
author: windows-driver-content
description: The EVT_POS_CX_DEVICE_OWNERSHIP_CHANGE callback is called during the API claim ownership transition. The driver is expected to set the device back to a default state in this routine.
old-location: pos\evt_pos_cx_device_ownership_change.htm
old-project: pos
ms.assetid: 9587928C-6C40-4550-820A-B77968E3E16A
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: *PPCFILTER_DESCRIPTOR, *PPCFILTER_DESCRIPTOR, PCFILTER_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: poscx.h
req.include-header: Poscx.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: EvtPosCxDeviceOwnershipChange
req.alt-loc: poscx.h
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
req.typenames: *PPCFILTER_DESCRIPTOR, PCFILTER_DESCRIPTOR
req.product: Windows 10 or later.
---

# EVT_POS_CX_DEVICE_OWNERSHIP_CHANGE callback



## -description
The 
  EVT_POS_CX_DEVICE_OWNERSHIP_CHANGE callback is called during the API claim ownership transition. The driver is expected to set the device back to a default state in this routine.



## -prototype

````
EVT_POS_CX_DEVICE_OWNERSHIP_CHANGE EvtPosCxDeviceOwnershipChange;

VOID EvtPosCxDeviceOwnershipChange(
  _In_     WDFDEVICE     device,
  _In_opt_ WDFFILEOBJECT oldOwnerFileObj,
  _In_opt_ WDFFILEOBJECT newOwnerFileObj
)
{ ... }
````


## -parameters

### -param device [in]

A handle to a framework device object that represents the device.


### -param oldOwnerFileObj [in, optional]

The file object of the previous claim owner. This may be NULL if no previous owner.


### -param newOwnerFileObj [in, optional]

The file object of the new claim owner. This may be NULL if the device was released without a pending claim request.


## -returns
This callback function does not return a value.

To define a <b>EVT_POS_CX_DEVICE_OWNERSHIP_CHANGE</b> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <b>EVT_POS_CX_DEVICE_OWNERSHIP_CHANGE</b> function that is named "MyEvtPosCxDeviceOwnershipChange", use the <b>EVT_POS_CX_DEVICE_OWNERSHIP_CHANGE</b> type as shown in this code example:

Then, implement your function as follows:

The <b>EVT_POS_CX_DEVICE_OWNERSHIP_CHANGE</b> function type is defined in the poscx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_POS_CX_DEVICE_OWNERSHIP_CHANGE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.


## -remarks

---
UID: NC:ntddk.DRIVER_REINITIALIZE
title: DRIVER_REINITIALIZE
author: windows-driver-content
description: The Reinitialize routine continues driver and device initialization after the driver's DriverEntry routine returns.
old-location: kernel\reinitialize.htm
old-project: kernel
ms.assetid: 5e883b80-a6e6-44b4-9e1c-78402b91edb9
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _FILTER_INITIALIZATION_DATA, *PFILTER_INITIALIZATION_DATA, FILTER_INITIALIZATION_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: Reinitialize
req.alt-loc: Ntddk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Called at PASSIVE_LEVEL.
req.typenames: *PFILTER_INITIALIZATION_DATA, FILTER_INITIALIZATION_DATA
---

# DRIVER_REINITIALIZE callback



## -description
The <i>Reinitialize</i> routine continues driver and device initialization after the driver's <b>DriverEntry</b> routine returns.



## -prototype

````
DRIVER_REINITIALIZE Reinitialize;

VOID Reinitialize(
  _In_     struct _DRIVER_OBJECT *DriverObject,
  _In_opt_ PVOID                 Context,
  _In_     ULONG                 Count
)
{ ... }
````


## -parameters

### -param DriverObject [in]

Caller-supplied pointer to a <a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a> structure. This is the driver's driver object.


### -param Context [in, optional]

Caller-supplied pointer to context information, specified in a previous call to <a href="..\ntddk\nf-ntddk-ioregisterdriverreinitialization.md">IoRegisterDriverReinitialization</a> or <a href="..\ntddk\nf-ntddk-ioregisterbootdriverreinitialization.md">IoRegisterBootDriverReinitialization</a>.


### -param Count [in]

Caller-supplied value representing the number of times the <i>Reinitialize</i> routine has been called, including the current call.


## -returns
None


## -remarks
To queue a <i>Reinitialize</i> routine for execution, a driver's <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine must call either <a href="..\ntddk\nf-ntddk-ioregisterdriverreinitialization.md">IoRegisterDriverReinitialization</a> or <a href="..\ntddk\nf-ntddk-ioregisterbootdriverreinitialization.md">IoRegisterBootDriverReinitialization</a>. The <i>Reinitialize</i> routine can also call <b>IoRegisterDriverReinitialization</b> itself, which causes the routine to be requeued. This requeuing can occur multiple times, and the routine's <i>Count</i> parameter indicates the number of times it has been called. The first call to <b>IoRegisterDriverReinitialization</b> must be made from <b>DriverEntry</b>, and <b>DriverEntry</b> must return STATUS_SUCCESS.

For more information about implementing a <i>Reinitialize</i> routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff566403">Writing a Reinitialize Routine</a>.

To define a <i>Reinitialize</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>Reinitialize</i> callback routine that is named <code>MyReinitialize</code>, use the DRIVER_REINITIALIZE type as shown in this code example:

Then, implement your callback routine as follows:

The DRIVER_REINITIALIZE function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the DRIVER_REINITIALIZE function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/3260b53e-82be-4dbc-8ac5-d0e52de77f9d">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.</p>
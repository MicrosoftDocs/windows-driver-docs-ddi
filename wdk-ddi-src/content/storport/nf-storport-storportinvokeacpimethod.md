---
UID: NF:storport.StorPortInvokeAcpiMethod
title: StorPortInvokeAcpiMethod function
author: windows-driver-content
description: The StorPortInvokeAcpiMethod routine executes an ACPI method for a storage device.
old-location: storage\storportinvokeacpimethod.htm
old-project: storage
ms.assetid: 2A8EF694-B699-46A0-9B1D-B7D0831F3944
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortInvokeAcpiMethod
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortInvokeAcpiMethod
req.alt-loc: storport.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortInvokeAcpiMethod function



## -description
The <b>StorPortInvokeAcpiMethod</b> routine executes an ACPI method for a storage device.



## -syntax

````
ULONG StorPortInvokeAcpiMethod(
  _In_      PVOID         HwDeviceExtension,
  _In_opt_  PSTOR_ADDRESS Address,
  _In_      ULONG         MethodName,
  _In_opt_  PVOID         InputBuffer,
  _In_      ULONG         InputBufferLength,
  _In_opt_  PVOID         OutputBuffer,
  _In_      ULONG         OutputBufferLength,
  _Out_opt_ PULONG        BytesReturned
);
````


## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param Address [in, optional]

The address of the target device. This parameter is optional. If <i>Address</i> is set to <b>NULL</b>, the adapter is the target.


### -param MethodName [in]

A four-byte name for the ACPI method. For example, ((ULONG) 'DDS_') would name the _SDD, or 'Set Device Data',  ACPI method for an AHCI controller.


### -param InputBuffer [in, optional]

A pointer to the input data to the method.


### -param InputBufferLength [in]

The length, in bytes, of the buffer in <i>InputBuffer</i>.


### -param OutputBuffer [in, optional]

A pointer to the output data from the method.


### -param OutputBufferLength [in]

The length, in bytes, of the buffer in <i>OutputBuffer</i>.


### -param BytesReturned [out, optional]

A pointer to the length, in bytes, of the data returned in <i>OutputBuffer</i>.


## -returns
The <b>StorPortInvokeAcpiMethod</b> routine returns one of these status codes:
<dl>
<dt><b>STOR_STATUS_INVALID_UNSUCCESSFUL</b></dt>
</dl>A general error condition exists.
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl><i>HwDeviceExtension</i>,  <i>InputBuffer</i>, or <i>OutputBuffer</i> is NULL.

-or-

<i>Address</i> refers to a target that does not exist.
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl> The ACPI method is not implemented.
<dl>
<dt><b>STOR_STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl> Insufficient resources are available to execute the method, or <i>OutputBufferLength</i> is not large enough for the returned data.
<dl>
<dt><b>STOR_STATUS_INVALID_IRQL</b></dt>
</dl>Current IRQL &gt; PASSIVE_LEVEL.
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>The method executed successfully.

 


## -remarks
The <b>StorPortInvokeAcpiMethod</b> enables a miniport driver to invoke ACPI methods defined for storage controllers and storage LUNs. The method names are four-byte character strings that occupy a <b>ULONG</b> value in <i>MethodName</i>.</p>
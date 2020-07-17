---
UID: NF:storport.StorPortInitialize
title: StorPortInitialize function (storport.h)
description: The StorPortInitilize routine initializes the port driver parameters and extension data. StorPortInitilize also saves the adapter information provided from the miniport driver.
old-location: storage\storportinitialize.htm
tech.root: storage
ms.assetid: b560ce42-3c5c-4766-bb9c-6590b7113ecd
ms.date: 03/29/2018
keywords: ["StorPortInitialize function"]
ms.keywords: StorPortInitialize, StorPortInitialize routine [Storage Devices], storage.storportinitialize, storport/StorPortInitialize, storprt_c60ad9af-507c-42e1-9f8a-04e3378bc37b.xml
f1_keywords:
 - "storport/StorPortInitialize"
 - "StorPortInitialize"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
req.lib: Storport.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Storport.lib
- Storport.dll
api_name:
- StorPortInitialize
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortInitialize function


## -description


The <b>StorPortInitialize</b> routine initializes the port driver parameters and extension data. <b>StorPortInitialize</b> also saves the adapter information provided from the [miniport driver](https://docs.microsoft.com/windows-hardware/drivers/storage/storage-miniport-drivers) DriverEntry routine.


## -parameters




### -param Argument1 [in]

The first pointer with which the operating system called the miniport's DriverEntry routine. 


### -param Argument2 [in]

The second pointer with which the operating system called the miniports's DriverEntry routine. 


### -param HwInitializationData [in]

Pointer to the initialization and configuration information set by the miniport driver in its DriverEntry routine. 


### -param HwContext [in, optional]

Is the address of a context value to be passed to the miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_find_adapter">HwStorFindAdapter</a> routine. Only legacy miniport drivers that scan the bus for HBAs rather than receiving configuration information from the port driver can use this parameter to store state between calls to <b>HwStorFindAdapter</b>. 


## -returns




      The result of the initialization actions performed by <b>StorPortInitialize</b>. The miniport driver will return this value as the return value for its DriverEntry routine.

<b>StorPortInitialize</b> returns one of the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
<i>Argument1</i> is NULL.

-or-

<i>Argument2</i> is NULL.

-or-

<i>HwInitializationData</i> is NULL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The driver extension data and adapter information were initialized successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b> STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
No memory is available to store an initialization parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b> STATUS_REVISION_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The version of the structure pointed to by <i>HwInitializationData</i> is invalid for the current operating system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b> STATUS_INSUFFICENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The allocation failed for the driver object extension data.

</td>
</tr>
</table>
 




## -remarks



This routine must be called from the miniport driver's DriverEntry routine.

Because Storport miniport drivers must support PnP, the Storport driver does not use the <i>HwContext</i> parameter passed to <b>StorPortInitialize</b>.

Every miniport driver's DriverEntry routine must call <b>StorPortInitialize</b> after the miniport driver has first zeroed and then set the members of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_hw_initialization_data-r1">HW_INITIALIZATION_DATA</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_initialization_data">HW_INITIALIZATION_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_find_adapter">HwStorFindAdapter</a>
 

 


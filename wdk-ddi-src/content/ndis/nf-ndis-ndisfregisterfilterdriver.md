---
UID: NF:ndis.NdisFRegisterFilterDriver
title: NdisFRegisterFilterDriver function
author: windows-driver-content
description: A filter driver calls the NdisFRegisterFilterDriver function to register its FilterXxx functions with NDIS.
old-location: netvista\ndisfregisterfilterdriver.htm
tech.root: netvista
ms.assetid: 14381de2-36d9-4ec8-9d4e-7af3e6d8ecf3
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: NdisFRegisterFilterDriver, NdisFRegisterFilterDriver function [Network Drivers Starting with Windows Vista], filter_ndis_functions_ref_a772ecb2-0cba-439e-82f1-928c3b40f3fd.xml, ndis/NdisFRegisterFilterDriver, netvista.ndisfregisterfilterdriver
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Filter_Driver_Function, NdisFDeregisterFilterDriver
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisFRegisterFilterDriver
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisFRegisterFilterDriver function


## -description


A filter driver calls the
  <b>
    NdisFRegisterFilterDriver</b> function to register its 
  <i>FilterXxx</i> functions with NDIS.


## -parameters




### -param DriverObject [in]

A pointer to an opaque driver object that the filter driver received in its 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine at the 
     <i>Argument1</i> parameter. (For more information, see 
     <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff548813">DriverEntry of NDIS Filter
     Drivers</a>.)


### -param FilterDriverContext [in]

A handle to a driver-allocated context area where the driver maintains state and configuration
     information.


### -param FilterDriverCharacteristics

A pointer to an 
     <a href="https://msdn.microsoft.com/1eb2bae0-70b9-4bc0-9d93-4fc9467f9532">
     NDIS_FILTER_DRIVER_CHARACTERISTICS</a> structure that the filter driver created and initialized with
     its 
     <i>FilterXxx</i> function entry points.

### -param NdisFilterDriverHandle [out]

A pointer to a handle variable. If the call to 
     <b>
    NdisFRegisterFilterDriver</b> succeeds, NDIS fills this variable with a filter driver handle. The
     filter driver saves this handle and later passes this handle to NDIS functions, such as 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff561800">NdisFDeregisterFilterDriver</a>,
     that require a filter driver handle as an input parameter.

## -returns



<b>
    NdisFRegisterFilterDriver</b> returns one of the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/14381de2-36d9-4ec8-9d4e-7af3e6d8ecf3">
    NdisFRegisterFilterDriver</a> returns NDIS_STATUS_SUCCESS if it registered the filter driver.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_BAD_VERSION</b></dt>
</dl>
</td>
<td width="60%">
The version that is specified in the 
       <b>MajorNdisVersion</b> member of the structure at 
       <i>FilterCharacteristics</i> is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_BAD_CHARACTERISTICS</b></dt>
</dl>
</td>
<td width="60%">
At least one of the members that are specified in 
       <a href="https://msdn.microsoft.com/1eb2bae0-70b9-4bc0-9d93-4fc9467f9532">
       NDIS_FILTER_DRIVER_CHARACTERISTICS</a> is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
At least one of the input parameters that the driver passed to 
       <a href="https://msdn.microsoft.com/14381de2-36d9-4ec8-9d4e-7af3e6d8ecf3">
    NdisFRegisterFilterDriver</a> is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/14381de2-36d9-4ec8-9d4e-7af3e6d8ecf3">
    NdisFRegisterFilterDriver</a> failed because of insufficient resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/14381de2-36d9-4ec8-9d4e-7af3e6d8ecf3">
    NdisFRegisterFilterDriver</a> returns NDIS_STATUS_FAILURE if none of the preceding values
       applies.

</td>
</tr>
</table>
 




## -remarks



A filter driver calls the 
    <b>
    NdisFRegisterFilterDriver</b> function from its 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine. For more information about 
    <b>DriverEntry</b>, see 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff548813">DriverEntry of NDIS Filter
    Drivers</a>.

Drivers that call <b>
    NdisFRegisterFilterDriver</b> must be prepared for an immediate call to any of their <i>FilterXxx</i> functions. For more information see <a href="https://msdn.microsoft.com/e24b18b5-76d3-4d56-bf60-0dea91ba014e">Initializing a Filter Driver</a>.

Every filter driver exports a set of 
    <i>FilterXxx</i> functions by setting up the 
    <a href="https://msdn.microsoft.com/1eb2bae0-70b9-4bc0-9d93-4fc9467f9532">
    NDIS_FILTER_DRIVER_CHARACTERISTICS</a> structure and calling 
    <b>
    NdisFRegisterFilterDriver</b>. NDIS copies this structure to the NDIS library's internal storage.

To allow filter drivers to register optional services, NDIS calls the 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">FilterSetOptions</a> function within the
    context of 
    <b>
    NdisFRegisterFilterDriver</b>.

After it has registered, a filter driver can later call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a> function
    to change the entry points for optional 
    <i>FilterXxx</i> functions.

Filter drivers call the 
    <a href="https://msdn.microsoft.com/f97ecce3-73b9-4c51-b4a4-e114420af2c9">
    NdisFDeregisterFilterDriver</a> function to release resources that were previously allocated with 
    <b>
    NdisFRegisterFilterDriver</b>.




## -see-also




<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff548813">DriverEntry of NDIS Filter
   Drivers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a>



<a href="https://msdn.microsoft.com/e24b18b5-76d3-4d56-bf60-0dea91ba014e">Initializing a Filter Driver</a>



<a href="https://msdn.microsoft.com/1eb2bae0-70b9-4bc0-9d93-4fc9467f9532">
   NDIS_FILTER_DRIVER_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561800">NdisFDeregisterFilterDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a>
 

 


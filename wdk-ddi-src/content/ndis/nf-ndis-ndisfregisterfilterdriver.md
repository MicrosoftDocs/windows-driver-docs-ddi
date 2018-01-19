---
UID: NF:ndis.NdisFRegisterFilterDriver
title: NdisFRegisterFilterDriver function
author: windows-driver-content
description: A filter driver calls the NdisFRegisterFilterDriver function to register its FilterXxx functions with NDIS.
old-location: netvista\ndisfregisterfilterdriver.htm
old-project: netvista
ms.assetid: 14381de2-36d9-4ec8-9d4e-7af3e6d8ecf3
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisFRegisterFilterDriver
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
req.alt-api: NdisFRegisterFilterDriver
req.alt-loc: ndis.lib,ndis.dll
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
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisFRegisterFilterDriver function



## -description
A filter driver calls the
  <b>
    NdisFRegisterFilterDriver</b> function to register its 
  <i>FilterXxx</i> functions with NDIS.



## -syntax

````
NDIS_STATUS NdisFRegisterFilterDriver(
  _In_  PDRIVER_OBJECT                      DriverObject,
  _In_  NDIS_HANDLE                         FilterDriverContext,
  _In_  PNDIS_FILTER_DRIVER_CHARACTERISTICS FilterCharacteristics,
  _Out_ PNDIS_HANDLE                        NdisFilterDriverHandle
);
````


## -parameters

### -param DriverObject [in]

A pointer to an opaque driver object that the filter driver received in its 
     <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine at the 
     <i>Argument1</i> parameter. (For more information, see 
     <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff548813">DriverEntry of NDIS Filter
     Drivers</a>.)


### -param FilterDriverContext [in]

A handle to a driver-allocated context area where the driver maintains state and configuration
     information.


### -param FilterCharacteristics [in]

A pointer to an 
     <a href="..\ndis\ns-ndis-_ndis_filter_driver_characteristics.md">
     NDIS_FILTER_DRIVER_CHARACTERISTICS</a> structure that the filter driver created and initialized with
     its 
     <i>FilterXxx</i> function entry points.


### -param NdisFilterDriverHandle [out]

A pointer to a handle variable. If the call to 
     <b>
    NdisFRegisterFilterDriver</b> succeeds, NDIS fills this variable with a filter driver handle. The
     filter driver saves this handle and later passes this handle to NDIS functions, such as 
     <a href="..\ndis\nf-ndis-ndisfderegisterfilterdriver.md">NdisFDeregisterFilterDriver</a>,
     that require a filter driver handle as an input parameter.


## -returns
<b>
    NdisFRegisterFilterDriver</b> returns one of the following status values:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
<a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">
    NdisFRegisterFilterDriver</a> returns NDIS_STATUS_SUCCESS if it registered the filter driver.
<dl>
<dt><b>NDIS_STATUS_BAD_VERSION</b></dt>
</dl>The version that is specified in the 
       <b>MajorNdisVersion</b> member of the structure at 
       <i>FilterCharacteristics</i> is invalid.
<dl>
<dt><b>NDIS_STATUS_BAD_CHARACTERISTICS</b></dt>
</dl>At least one of the members that are specified in 
       <a href="..\ndis\ns-ndis-_ndis_filter_driver_characteristics.md">
       NDIS_FILTER_DRIVER_CHARACTERISTICS</a> is invalid.
<dl>
<dt><b>NDIS_STATUS_INVALID_PARAMETER</b></dt>
</dl>At least one of the input parameters that the driver passed to 
       <a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">
    NdisFRegisterFilterDriver</a> is invalid.
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
<a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">
    NdisFRegisterFilterDriver</a> failed because of insufficient resources.
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
<a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">
    NdisFRegisterFilterDriver</a> returns NDIS_STATUS_FAILURE if none of the preceding values
       applies.

 


## -remarks
A filter driver calls the 
    <b>
    NdisFRegisterFilterDriver</b> function from its 
    <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine. For more information about 
    <b>DriverEntry</b>, see 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff548813">DriverEntry of NDIS Filter
    Drivers</a>.

Drivers that call <b>
    NdisFRegisterFilterDriver</b> must be prepared for an immediate call to any of their <i>FilterXxx</i> functions. For more information see <a href="https://msdn.microsoft.com/e24b18b5-76d3-4d56-bf60-0dea91ba014e">Initializing a Filter Driver</a>.

Every filter driver exports a set of 
    <i>FilterXxx</i> functions by setting up the 
    <a href="..\ndis\ns-ndis-_ndis_filter_driver_characteristics.md">
    NDIS_FILTER_DRIVER_CHARACTERISTICS</a> structure and calling 
    <b>
    NdisFRegisterFilterDriver</b>. NDIS copies this structure to the NDIS library's internal storage.

To allow filter drivers to register optional services, NDIS calls the 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">FilterSetOptions</a> function within the
    context of 
    <b>
    NdisFRegisterFilterDriver</b>.

After it has registered, a filter driver can later call the 
    <a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a> function
    to change the entry points for optional 
    <i>FilterXxx</i> functions.

Filter drivers call the 
    <a href="..\ndis\nf-ndis-ndisfderegisterfilterdriver.md">
    NdisFDeregisterFilterDriver</a> function to release resources that were previously allocated with 
    <b>
    NdisFRegisterFilterDriver</b>.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff548813">DriverEntry of NDIS Filter
   Drivers</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_filter_driver_characteristics.md">
   NDIS_FILTER_DRIVER_CHARACTERISTICS</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisfderegisterfilterdriver.md">NdisFDeregisterFilterDriver</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/e24b18b5-76d3-4d56-bf60-0dea91ba014e">Initializing a Filter Driver</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFRegisterFilterDriver function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


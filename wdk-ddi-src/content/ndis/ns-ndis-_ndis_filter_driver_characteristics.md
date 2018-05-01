---
UID: NS:ndis._NDIS_FILTER_DRIVER_CHARACTERISTICS
title: "_NDIS_FILTER_DRIVER_CHARACTERISTICS"
author: windows-driver-content
description: To specify its driver characteristics, a filter driver initializes an NDIS_FILTER_DRIVER_CHARACTERISTICS structure and passes it to NDIS.
old-location: netvista\ndis_filter_driver_characteristics.htm
old-project: netvista
ms.assetid: 1eb2bae0-70b9-4bc0-9d93-4fc9467f9532
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PNDIS_FILTER_DRIVER_CHARACTERISTICS, NDIS_FILTER_DRIVER_CHARACTERISTICS, NDIS_FILTER_DRIVER_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_FILTER_DRIVER_CHARACTERISTICS, PNDIS_FILTER_DRIVER_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_FILTER_DRIVER_CHARACTERISTICS, filter_structures_ref_8fc4ed95-82fe-47bd-849d-f9733647cacd.xml, ndis/NDIS_FILTER_DRIVER_CHARACTERISTICS, ndis/PNDIS_FILTER_DRIVER_CHARACTERISTICS, netvista.ndis_filter_driver_characteristics"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
-	ndis.h
api_name:
-	NDIS_FILTER_DRIVER_CHARACTERISTICS
product: Windows
targetos: Windows
req.typenames: NDIS_FILTER_DRIVER_CHARACTERISTICS, *PNDIS_FILTER_DRIVER_CHARACTERISTICS
---

# _NDIS_FILTER_DRIVER_CHARACTERISTICS structure


## -description


To specify its driver characteristics, a filter driver initializes an
  NDIS_FILTER_DRIVER_CHARACTERISTICS structure and passes it to NDIS.


## -struct-fields




### -field Header

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     filter driver characteristics structure (NDIS_FILTER_DRIVER_CHARACTERISTICS). Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_FILTER_DRIVER_CHARACTERISTICS.
     

To indicate the version of the NDIS_FILTER_DRIVER_CHARACTERISTICS structure, set the 
     <b>Revision</b> member to one of the following values:





#### NDIS_FILTER_CHARACTERISTICS_REVISION_3

Added the 
        <b>SynchronousOidRequestHandler</b> and <b>SynchronousOidRequestHandlerComplete</b> members for NDIS 6.80.

Set the 
        <b>Size</b> member to NDIS_SIZEOF_FILTER_DRIVER_CHARACTERISTICS_REVISION_3.



#### NDIS_FILTER_CHARACTERISTICS_REVISION_2

Added the 
        <b>DirectOidRequestHandler</b>, 
        <b>DirectOidRequestCompleteHandler</b>, and 
        <b>CancelDirectOidRequestHandler</b> members for NDIS 6.1.

Set the 
        <b>Size</b> member to NDIS_SIZEOF_FILTER_DRIVER_CHARACTERISTICS_REVISION_2.



#### NDIS_FILTER_CHARACTERISTICS_REVISION_1

Original version.

Set the 
        <b>Size</b> member to NDIS_SIZEOF_FILTER_DRIVER_CHARACTERISTICS_REVISION_1.


### -field MajorNdisVersion

The major version of NDIS that the driver is using. The current value is
     0x06.


### -field MinorNdisVersion

The minor NDIS version. The following are the available minor version value settings.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0</dt>
</dl>
</td>
<td width="60%">
NDIS 6

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>20</dt>
</dl>
</td>
<td width="60%">
NDIS 6.20

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>30</dt>
</dl>
</td>
<td width="60%">
NDIS 6.30

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>40</dt>
</dl>
</td>
<td width="60%">
NDIS 6.40

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>50</dt>
</dl>
</td>
<td width="60%">
NDIS 6.50

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>51</dt>
</dl>
</td>
<td width="60%">
NDIS 6.51

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>60</dt>
</dl>
</td>
<td width="60%">
NDIS 6.60

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>70</dt>
</dl>
</td>
<td width="60%">
NDIS 6.70

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>80</dt>
</dl>
</td>
<td width="60%">
NDIS 6.80

</td>
</tr>
</table>
 


### -field MajorDriverVersion

Reserved for the major version number of the filter driver. Filter drivers can specify any value
     that they require.


### -field MinorDriverVersion

Reserved for the minor version number of the filter driver. Filter drivers can specify any value
     that they require.


### -field Flags

Reserved for NDIS.


### -field FriendlyName

A Unicode string that represents the user-readable description of the filter driver.


### -field UniqueName

A Unicode string that represents the unique name for the filter driver. This string must be a GUID, enclosed in curly braces, for example "{5cbf81bd-5055-47cd-9055-a76b2b4e3697}". This GUID must match the one in the <b>NetCfgInstanceId</b> INF file entry in the filter driver's INF file. For more information, see <a href="https://msdn.microsoft.com/e2714e67-62ac-4d9a-bec3-971d1c8b5bd8">INF File Settings for Filter Drivers</a>.


### -field ServiceName

A Unicode string that represents the service name of the filter driver. This string must be the service name
     from the AddService directive in the filter driver's INF file. For more information, see <a href="https://msdn.microsoft.com/e2714e67-62ac-4d9a-bec3-971d1c8b5bd8">INF File Settings for Filter Drivers</a>.


### -field SetOptionsHandler

Specifies the entry point of the caller's 
     <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">FilterSetOptions</a> function.


### -field SetFilterModuleOptionsHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/04b7ac32-8996-4648-8c88-aa9f630b1bc4">
     FilterSetModuleOptions</a> function.


### -field AttachHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a> function.


### -field DetachHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff540475">FilterDetach</a> function.


### -field RestartHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/4a917824-eef1-4945-b45e-1c940bc8a50d">FilterRestart</a> function.


### -field PauseHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/a239889e-ec39-48fc-9e82-c8bc3d7ca51a">FilterPause</a> function.


### -field SendNetBufferListsHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/1b3fc0c8-95da-47e5-8ff1-b7967f5148e7">
     FilterSendNetBufferLists</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field SendNetBufferListsCompleteHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/1a3a1e80-29f1-4f19-b3c7-9a8b189f18c4">
     FilterSendNetBufferListsComplete</a> function. To bypass this function, set this member to
     <b>NULL</b>.


### -field CancelSendNetBufferListsHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/55979b0d-61a6-43da-8fa5-11159b1a48d1">
     FilterCancelSendNetBufferLists</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field ReceiveNetBufferListsHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/6359c2a7-1208-41ea-bbf9-015c91b6e8f6">
     FilterReceiveNetBufferLists</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field ReturnNetBufferListsHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/8d7e362f-62da-4ce7-9497-1cfaff2b678e">
     FilterReturnNetBufferLists</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field OidRequestHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/238bfa21-a971-4fe4-a774-6ba834efc3c5">FilterOidRequest</a> function. To bypass
     this function, set this member to <b>NULL</b>.


### -field OidRequestCompleteHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/2dba21d8-512b-4a1a-9cf9-0240c94a69a0">
     FilterOidRequestComplete</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field CancelOidRequestHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/e7e3f67e-5353-4355-bf19-8a8041cafc84">
     FilterCancelOidRequest</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field DevicePnPEventNotifyHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/dea4ab30-ba1d-4c9c-9f00-e48cc3cc0b46">
     FilterDevicePnPEventNotify</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field NetPnPEventHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/5c52b2d2-3fba-4d28-8172-7b6854386061">FilterNetPnPEvent</a> function. To
     bypass this function, set this member to <b>NULL</b>.


### -field StatusHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/051ce37c-a7a5-4367-9495-023fc51349ba">FilterStatus</a> function. To bypass this
     function, set this member to <b>NULL</b>.


### -field DirectOidRequestHandler

The entry point of the caller's 
      <a href="https://msdn.microsoft.com/a39f4b50-0183-4f92-82f2-3c8e2e2d0632">
      FilterDirectOidRequest</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field DirectOidRequestCompleteHandler

The entry point of the caller's 
      <a href="https://msdn.microsoft.com/a97c86e9-4fd9-4e2f-9787-4fa19c38a69b">
      FilterDirectOidRequestComplete</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field CancelDirectOidRequestHandler

The entry point of the caller's 
      <a href="https://msdn.microsoft.com/3587c5dc-3b4c-4aab-8c2d-cc9988373a56">
      FilterCancelDirectOidRequest</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field SynchronousOidRequestHandler

<div class="alert"><b>Warning</b>  In Windows 10, version 1709, Synchronous OID requests are supported only for miniport and protocol drivers. Filter drivers cannot make Synchronous OID request calls in Windows 10, version 1709.</div>
<div> </div>
This member is reserved.


### -field SynchronousOidRequestCompleteHandler

 




#### - SynchronousOidRequestHandlerComplete

<div class="alert"><b>Warning</b>  In Windows 10, version 1709, Synchronous OID requests are supported only for miniport and protocol drivers. Filter drivers cannot make Synchronous OID request calls in Windows 10, version 1709.</div>
<div> </div>
This member is reserved.


## -remarks



A filter driver calls the 
    <a href="https://msdn.microsoft.com/14381de2-36d9-4ec8-9d4e-7af3e6d8ecf3">
    NdisFRegisterFilterDriver</a> function to register its characteristics, including the default entry
    points for its filter driver functions (<i>FilterXxx</i>). The filter driver initializes an NDIS_FILTER_DRIVER_CHARACTERISTICS structure and
    passes a pointer to this structure in the 
    <i>FilterCharacteristics</i> parameter of 
    <b>NdisFRegisterFilterDriver</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a>



<a href="https://msdn.microsoft.com/3587c5dc-3b4c-4aab-8c2d-cc9988373a56">
   FilterCancelDirectOidRequest</a>



<a href="https://msdn.microsoft.com/e7e3f67e-5353-4355-bf19-8a8041cafc84">FilterCancelOidRequest</a>



<a href="https://msdn.microsoft.com/55979b0d-61a6-43da-8fa5-11159b1a48d1">
   FilterCancelSendNetBufferLists</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540475">FilterDetach</a>



<a href="https://msdn.microsoft.com/dea4ab30-ba1d-4c9c-9f00-e48cc3cc0b46">FilterDevicePnPEventNotify</a>



<a href="https://msdn.microsoft.com/a39f4b50-0183-4f92-82f2-3c8e2e2d0632">FilterDirectOidRequest</a>



<a href="https://msdn.microsoft.com/a97c86e9-4fd9-4e2f-9787-4fa19c38a69b">
   FilterDirectOidRequestComplete</a>



<a href="https://msdn.microsoft.com/5c52b2d2-3fba-4d28-8172-7b6854386061">FilterNetPnPEvent</a>



<a href="https://msdn.microsoft.com/238bfa21-a971-4fe4-a774-6ba834efc3c5">FilterOidRequest</a>



<a href="https://msdn.microsoft.com/2dba21d8-512b-4a1a-9cf9-0240c94a69a0">FilterOidRequestComplete</a>



<a href="https://msdn.microsoft.com/a239889e-ec39-48fc-9e82-c8bc3d7ca51a">FilterPause</a>



<a href="https://msdn.microsoft.com/6359c2a7-1208-41ea-bbf9-015c91b6e8f6">FilterReceiveNetBufferLists</a>



<a href="https://msdn.microsoft.com/4a917824-eef1-4945-b45e-1c940bc8a50d">FilterRestart</a>



<a href="https://msdn.microsoft.com/8d7e362f-62da-4ce7-9497-1cfaff2b678e">FilterReturnNetBufferLists</a>



<a href="https://msdn.microsoft.com/1b3fc0c8-95da-47e5-8ff1-b7967f5148e7">FilterSendNetBufferLists</a>



<a href="https://msdn.microsoft.com/1a3a1e80-29f1-4f19-b3c7-9a8b189f18c4">
   FilterSendNetBufferListsComplete</a>



<a href="https://msdn.microsoft.com/04b7ac32-8996-4648-8c88-aa9f630b1bc4">FilterSetModuleOptions</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">FilterSetOptions</a>



<a href="https://msdn.microsoft.com/051ce37c-a7a5-4367-9495-023fc51349ba">FilterStatus</a>



<a href="https://msdn.microsoft.com/e2714e67-62ac-4d9a-bec3-971d1c8b5bd8">INF File Settings for Filter Drivers</a>



<a href="https://msdn.microsoft.com/e24b18b5-76d3-4d56-bf60-0dea91ba014e">Initializing a Filter Driver</a>



<a href="https://msdn.microsoft.com/4a7f365c-a252-4d8e-bddf-684b3298db5c">
   NDIS_FILTER_PARTIAL_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562608">NdisFRegisterFilterDriver</a>
 

 


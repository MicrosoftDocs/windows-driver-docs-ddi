---
UID: NS:ndis._NDIS_PROTOCOL_DRIVER_CHARACTERISTICS
title: "_NDIS_PROTOCOL_DRIVER_CHARACTERISTICS"
author: windows-driver-content
description: To specify its driver characteristics, a protocol driver initializes an NDIS_PROTOCOL_DRIVER_CHARACTERISTICS structure and passes it to NDIS.
old-location: netvista\ndis_protocol_driver_characteristics.htm
tech.root: netvista
ms.assetid: db64c160-9db6-4b23-af14-e64acdb9ef57
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: "*PNDIS_PROTOCOL_DRIVER_CHARACTERISTICS, NDIS_PROTOCOL_DRIVER_CHARACTERISTICS, NDIS_PROTOCOL_DRIVER_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_PROTOCOL_DRIVER_CHARACTERISTICS, PNDIS_PROTOCOL_DRIVER_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PROTOCOL_DRIVER_CHARACTERISTICS, ndis/NDIS_PROTOCOL_DRIVER_CHARACTERISTICS, ndis/PNDIS_PROTOCOL_DRIVER_CHARACTERISTICS, netvista.ndis_protocol_driver_characteristics, protocol_structures_ref_57fab3c7-f838-4a3f-a818-04d26e38cdc0.xml"
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
-	NDIS_PROTOCOL_DRIVER_CHARACTERISTICS
product:
- Windows
targetos: Windows
req.typenames: NDIS_PROTOCOL_DRIVER_CHARACTERISTICS, *PNDIS_PROTOCOL_DRIVER_CHARACTERISTICS
---

# _NDIS_PROTOCOL_DRIVER_CHARACTERISTICS structure


## -description


To specify its driver characteristics, a protocol driver initializes an
  <b>NDIS_PROTOCOL_DRIVER_CHARACTERISTICS</b> structure and passes it to NDIS.


## -struct-fields




### -field Header

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_PROTOCOL_DRIVER_CHARACTERISTICS</b> structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_PROTOCOL_DRIVER_CHARACTERISTICS.
     

To indicate the version of the <b>NDIS_PROTOCOL_DRIVER_CHARACTERISTICS</b> structure, set the 
     <b>Revision</b> member to one of the following values:





#### NDIS_PROTOCOL_DRIVER_CHARACTERISTICS_REVISION_2

Added the 
        <b>DirectOidRequestCompleteHandler</b> member for NDIS 6.1.

Set the 
        <b>Size</b> member to
        NDIS_SIZEOF_PROTOCOL_DRIVER_CHARACTERISTICS_REVISION_2.



#### NDIS_PROTOCOL_DRIVER_CHARACTERISTICS_REVISION_1

Original version for NDIS 6.0.

Set the 
        <b>Size</b> member to
        NDIS_SIZEOF_PROTOCOL_DRIVER_CHARACTERISTICS_REVISION_1.


### -field MajorNdisVersion

The major version of the NDIS library the protocol driver is using. The current value is
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

<tr>
<td width="40%">
<dl>
<dt>81</dt>
</dl>
</td>
<td width="60%">
NDIS 6.81

</td>
</tr>
</table>
 


### -field MajorDriverVersion

Reserved for the major version number of the protocol driver. Protocol drivers can specify any
     value that they require.


### -field MinorDriverVersion

Reserved for the minor version number of the protocol driver. Protocol drivers can specify any
     value that they require.


### -field Flags

Reserved for NDIS. Protocol drivers should set this member to zero.


### -field Name

A Unicode string that is the service name of the protocol driver.


### -field SetOptionsHandler

The entry point for the 
     <a href="https://msdn.microsoft.com/342e23ad-d38b-4100-949a-220b8fbdcf6e">ProtocolSetOptions</a> function.


### -field BindAdapterHandlerEx

The entry point for the 
     <a href="https://msdn.microsoft.com/1958722e-012e-4110-a82c-751744bcf9b5">
     ProtocolBindAdapterEx</a> function.


### -field UnbindAdapterHandlerEx

The entry point for the 
     <a href="https://msdn.microsoft.com/19fa7be2-acb9-42f6-bd9f-5be3e3c8b5fa">
     ProtocolUnbindAdapterEx</a> function.


### -field OpenAdapterCompleteHandlerEx

The entry point for the 
     <a href="https://msdn.microsoft.com/59d18822-8ce2-4506-90d7-9f1cdc7a9e10">
     ProtocolOpenAdapterCompleteEx</a> function.


### -field CloseAdapterCompleteHandlerEx

The entry point for the 
     <a href="https://msdn.microsoft.com/62cc047a-bc91-4e1e-817e-7fd509d4d90e">
     ProtocolCloseAdapterCompleteEx</a> function.


### -field NetPnPEventHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/3f50bcba-c7d2-4d81-bd8b-6080e08fbe74">ProtocolNetPnPEvent</a> function.


### -field UninstallHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/959baf54-849c-4bb1-b4c5-4d5537e1d688">ProtocolUninstall</a> function, if any,
     or <b>NULL</b>.


### -field OidRequestCompleteHandler

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/2706577e-ba03-4347-9672-7303752ec0fe">
     ProtocolOidRequestComplete</a> function.


### -field StatusHandlerEx

The entry point of the caller's 
     <a href="https://msdn.microsoft.com/5bc5a24f-5f28-4502-8776-b1cf15fd8283">ProtocolStatusEx</a> function, if any, or
     <b>NULL</b>.


### -field ReceiveNetBufferListsHandler

The entry point for the 
     <a href="https://msdn.microsoft.com/c964b4b8-ab07-4a07-9965-5cc06c028c20">
     ProtocolReceiveNetBufferLists</a> function.


### -field SendNetBufferListsCompleteHandler

The entry point for the 
     <a href="https://msdn.microsoft.com/bc9197c5-ce0b-42b2-8225-fb9d83427ac8">
     ProtocolSendNetBufferListsComplete</a> function.


### -field DirectOidRequestCompleteHandler

The entry point of the caller's 
      <a href="https://msdn.microsoft.com/6b23bbba-1b18-4da7-a45c-68df7c960aad">
      ProtocolDirectOidRequestComplete</a> function. This is an optional function. Set this entry point to
      <b>NULL</b> if the protocol driver does not support the direct OID request interface.


## -remarks



A protocol driver calls the 
    <a href="https://msdn.microsoft.com/b48571eb-13a2-4541-80ac-c8d31f378d37">
    NdisRegisterProtocolDriver</a> function to register its characteristics, including the default entry
    points for its protocol driver functions (<i>ProtocolXxx</i>). The protocol driver initializes an <b>NDIS_PROTOCOL_DRIVER_CHARACTERISTICS</b> structure
    and passes a pointer to this structure in the 
    <i>ProtocolCharacteristics</i> parameter of 
    <b>NdisRegisterProtocolDriver</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564520">NdisRegisterProtocolDriver</a>



<a href="https://msdn.microsoft.com/1958722e-012e-4110-a82c-751744bcf9b5">ProtocolBindAdapterEx</a>



<a href="https://msdn.microsoft.com/62cc047a-bc91-4e1e-817e-7fd509d4d90e">
   ProtocolCloseAdapterCompleteEx</a>



<a href="https://msdn.microsoft.com/6b23bbba-1b18-4da7-a45c-68df7c960aad">
   ProtocolDirectOidRequestComplete</a>



<a href="https://msdn.microsoft.com/3f50bcba-c7d2-4d81-bd8b-6080e08fbe74">ProtocolNetPnPEvent</a>



<a href="https://msdn.microsoft.com/2706577e-ba03-4347-9672-7303752ec0fe">ProtocolOidRequestComplete</a>



<a href="https://msdn.microsoft.com/59d18822-8ce2-4506-90d7-9f1cdc7a9e10">
   ProtocolOpenAdapterCompleteEx</a>



<a href="https://msdn.microsoft.com/c964b4b8-ab07-4a07-9965-5cc06c028c20">
   ProtocolReceiveNetBufferLists</a>



<a href="https://msdn.microsoft.com/bc9197c5-ce0b-42b2-8225-fb9d83427ac8">
   ProtocolSendNetBufferListsComplete</a>



<a href="https://msdn.microsoft.com/342e23ad-d38b-4100-949a-220b8fbdcf6e">ProtocolSetOptions</a>



<a href="https://msdn.microsoft.com/5bc5a24f-5f28-4502-8776-b1cf15fd8283">ProtocolStatusEx</a>



<a href="https://msdn.microsoft.com/19fa7be2-acb9-42f6-bd9f-5be3e3c8b5fa">ProtocolUnbindAdapterEx</a>



<a href="https://msdn.microsoft.com/959baf54-849c-4bb1-b4c5-4d5537e1d688">ProtocolUninstall</a>
 

 


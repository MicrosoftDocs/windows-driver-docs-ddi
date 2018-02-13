---
UID: NS:ndis._NDIS_PROTOCOL_DRIVER_CHARACTERISTICS
title: "_NDIS_PROTOCOL_DRIVER_CHARACTERISTICS"
author: windows-driver-content
description: To specify its driver characteristics, a protocol driver initializes an NDIS_PROTOCOL_DRIVER_CHARACTERISTICS structure and passes it to NDIS.
old-location: netvista\ndis_protocol_driver_characteristics.htm
old-project: netvista
ms.assetid: db64c160-9db6-4b23-af14-e64acdb9ef57
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*PNDIS_PROTOCOL_DRIVER_CHARACTERISTICS, netvista.ndis_protocol_driver_characteristics, PNDIS_PROTOCOL_DRIVER_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], PNDIS_PROTOCOL_DRIVER_CHARACTERISTICS, protocol_structures_ref_57fab3c7-f838-4a3f-a818-04d26e38cdc0.xml, NDIS_PROTOCOL_DRIVER_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], NDIS_PROTOCOL_DRIVER_CHARACTERISTICS, ndis/PNDIS_PROTOCOL_DRIVER_CHARACTERISTICS, _NDIS_PROTOCOL_DRIVER_CHARACTERISTICS, ndis/NDIS_PROTOCOL_DRIVER_CHARACTERISTICS"
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
req.irql: See Remarks section
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
-	NDIS_PROTOCOL_DRIVER_CHARACTERISTICS
product: Windows
targetos: Windows
req.typenames: "*PNDIS_PROTOCOL_DRIVER_CHARACTERISTICS, NDIS_PROTOCOL_DRIVER_CHARACTERISTICS"
---

# _NDIS_PROTOCOL_DRIVER_CHARACTERISTICS structure


## -description


To specify its driver characteristics, a protocol driver initializes an
  <b>NDIS_PROTOCOL_DRIVER_CHARACTERISTICS</b> structure and passes it to NDIS.


## -syntax


````
typedef struct _NDIS_PROTOCOL_DRIVER_CHARACTERISTICS {
  NDIS_OBJECT_HEADER                     Header;
  UCHAR                                  MajorNdisVersion;
  UCHAR                                  MinorNdisVersion;
  UCHAR                                  MajorDriverVersion;
  UCHAR                                  MinorDriverVersion;
  ULONG                                  Flags;
  NDIS_STRING                            Name;
  SET_OPTIONS_HANDLER                    SetOptionsHandler;
  BIND_HANDLER_EX                        BindAdapterHandlerEx;
  UNBIND_HANDLER_EX                      UnbindAdapterHandlerEx;
  OPEN_ADAPTER_COMPLETE_HANDLER_EX       OpenAdapterCompleteHandlerEx;
  CLOSE_ADAPTER_COMPLETE_HANDLER_EX      CloseAdapterCompleteHandlerEx;
  NET_PNP_EVENT_HANDLER                  NetPnPEventHandler;
  UNINSTALL_PROTOCOL_HANDLER             UninstallHandler;
  OID_REQUEST_COMPLETE_HANDLER           OidRequestCompleteHandler;
  STATUS_HANDLER_EX                      StatusHandlerEx;
  RECEIVE_NET_BUFFER_LISTS_HANDLER       ReceiveNetBufferListsHandler;
  SEND_NET_BUFFER_LISTS_COMPLETE_HANDLER SendNetBufferListsCompleteHandler;
#if (NDIS_SUPPORT_NDIS61)
  DIRECT_OID_REQUEST_COMPLETE_HANDLER    DirectOidRequestCompleteHandler;
#endif 
} NDIS_PROTOCOL_DRIVER_CHARACTERISTICS, *PNDIS_PROTOCOL_DRIVER_CHARACTERISTICS;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
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
     <a href="..\ndis\nc-ndis-set_options.md">ProtocolSetOptions</a> function.


### -field BindAdapterHandlerEx

The entry point for the 
     <a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">
     ProtocolBindAdapterEx</a> function.


### -field UnbindAdapterHandlerEx

The entry point for the 
     <a href="..\ndis\nc-ndis-protocol_unbind_adapter_ex.md">
     ProtocolUnbindAdapterEx</a> function.


### -field OpenAdapterCompleteHandlerEx

The entry point for the 
     <a href="..\ndis\nc-ndis-protocol_open_adapter_complete_ex.md">
     ProtocolOpenAdapterCompleteEx</a> function.


### -field CloseAdapterCompleteHandlerEx

The entry point for the 
     <a href="..\ndis\nc-ndis-protocol_close_adapter_complete_ex.md">
     ProtocolCloseAdapterCompleteEx</a> function.


### -field NetPnPEventHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_net_pnp_event.md">ProtocolNetPnPEvent</a> function.


### -field UninstallHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_uninstall.md">ProtocolUninstall</a> function, if any,
     or <b>NULL</b>.


### -field OidRequestCompleteHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_oid_request_complete.md">
     ProtocolOidRequestComplete</a> function.


### -field StatusHandlerEx

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-protocol_status_ex.md">ProtocolStatusEx</a> function, if any, or
     <b>NULL</b>.


### -field ReceiveNetBufferListsHandler

The entry point for the 
     <a href="..\ndis\nc-ndis-protocol_receive_net_buffer_lists.md">
     ProtocolReceiveNetBufferLists</a> function.


### -field SendNetBufferListsCompleteHandler

The entry point for the 
     <a href="..\ndis\nc-ndis-protocol_send_net_buffer_lists_complete.md">
     ProtocolSendNetBufferListsComplete</a> function.


### -field DirectOidRequestCompleteHandler

The entry point of the caller's 
      <a href="..\ndis\nc-ndis-protocol_direct_oid_request_complete.md">
      ProtocolDirectOidRequestComplete</a> function. This is an optional function. Set this entry point to
      <b>NULL</b> if the protocol driver does not support the direct OID request interface.


## -remarks



A protocol driver calls the 
    <a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">
    NdisRegisterProtocolDriver</a> function to register its characteristics, including the default entry
    points for its protocol driver functions (<i>ProtocolXxx</i>). The protocol driver initializes an <b>NDIS_PROTOCOL_DRIVER_CHARACTERISTICS</b> structure
    and passes a pointer to this structure in the 
    <i>ProtocolCharacteristics</i> parameter of 
    <b>NdisRegisterProtocolDriver</b>.




## -see-also

<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>



<a href="..\ndis\nc-ndis-protocol_receive_net_buffer_lists.md">
   ProtocolReceiveNetBufferLists</a>



<a href="..\ndis\nc-ndis-protocol_open_adapter_complete_ex.md">
   ProtocolOpenAdapterCompleteEx</a>



<a href="..\ndis\nc-ndis-protocol_status_ex.md">ProtocolStatusEx</a>



<a href="..\ndis\nc-ndis-protocol_oid_request_complete.md">ProtocolOidRequestComplete</a>



<a href="..\ndis\nc-ndis-protocol_net_pnp_event.md">ProtocolNetPnPEvent</a>



<a href="..\ndis\nc-ndis-protocol_direct_oid_request_complete.md">
   ProtocolDirectOidRequestComplete</a>



<a href="..\ndis\nc-ndis-protocol_unbind_adapter_ex.md">ProtocolUnbindAdapterEx</a>



<a href="..\ndis\nc-ndis-set_options.md">ProtocolSetOptions</a>



<a href="..\ndis\nc-ndis-protocol_send_net_buffer_lists_complete.md">
   ProtocolSendNetBufferListsComplete</a>



<a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">NdisRegisterProtocolDriver</a>



<a href="..\ndis\nc-ndis-protocol_close_adapter_complete_ex.md">
   ProtocolCloseAdapterCompleteEx</a>



<a href="..\ndis\nc-ndis-protocol_uninstall.md">ProtocolUninstall</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PROTOCOL_DRIVER_CHARACTERISTICS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


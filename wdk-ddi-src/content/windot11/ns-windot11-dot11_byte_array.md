---
UID: NS:windot11.DOT11_BYTE_ARRAY
title: DOT11_BYTE_ARRAY
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_byte_array.htm
old-project: netvista
ms.assetid: a2c67eaf-d39e-43c9-8e06-18f668c0baa3
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: DOT11_BYTE_ARRAY, *PDOT11_BYTE_ARRAY, DOT11_BYTE_ARRAY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_BYTE_ARRAY
req.alt-loc: windot11.h
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
req.typenames: *PDOT11_BYTE_ARRAY, DOT11_BYTE_ARRAY
req.product: Windows 10 or later.
---

# DOT11_BYTE_ARRAY structure



## -description

## -syntax

````
typedef struct DOT11_BYTE_ARRAY {
  NDIS_OBJECT_HEADER Header;
  ULONG              uNumOfBytes;
  ULONG              uTotalNumOfBytes;
  UCHAR              ucBuffer[1];
} DOT11_BYTE_ARRAY, *PDOT11_BYTE_ARRAY;
````


## -struct-fields

### -field Header

The type, revision, and size of the DOT11_BYTE_ARRAY structure. This member is formatted as an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.
     

The miniport driver must set the members of 
     <b>Header</b> to the following values:




### -field Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.


### -field Revision

This member must be set to the revision of the variable-length structures which follow the
       DOT11_BYTE_ARRAY structure. For more information about the revision of these structures, refer to the
       object identifiers (OIDS) listed in the 
       "See Also" section.


### -field Size

This member must be set to 
       sizeof(DOT11_BYTE_ARRAY).

</dd>
</dl>
For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field uNumOfBytes

The number of bytes in the 
     <b>ucBuffer</b> array.


### -field uTotalNumOfBytes

The maximum number of bytes that the 
     <b>ucBuffer</b> array requires.


### -field ucBuffer

The list of variable-length structures.


## -remarks
The type of structures stored in the 
    <b>ucBuffer</b> array depends on the OID set and query request. For example, when queried by 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569360">OID_DOT11_ENUM_BSS_LIST</a>, a miniport
    driver stores one or more DOT11_BSS_ENTRY structures in the 
    <b>ucBuffer</b> array.

When queried by an OID that uses the DOT11_BYTE_ARRAY structure, the miniport driver must verify that
    the 
    <b>InformationBuffer</b> member of the 
    <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function's
    <i>OidRequest</i> parameter is large enough to return the entire structure, including all entries in the 
    <b>ucBuffer</b> array. The value of the 
    <b>InformationBufferLength</b> member of the 
    <i>OidRequest</i> parameter determines what the miniport driver must do, as the following list shows:

If the value of the 
      <b>InformationBufferLength</b> member is less than the length, in bytes, of the entire DOT11_BYTE_ARRAY
      structure, the miniport driver must do the following:

For the 
        <i>OidRequest</i> parameter, set the 
        <b>BytesWritten</b> member to zero and the 
        <b>BytesNeeded</b> member to the length, in bytes, of the entire DOT11_BYTE_ARRAY structure

Fail the query request by returning NDIS_STATUS_BUFFER_OVERFLOW from its 
        <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function.

If the value of the 
      <b>InformationBufferLength</b> member is greater than or equal to the length, in bytes, of the entire
      DOT11_BYTE_ARRAY structure, the miniport driver must do the following to complete a successful query
      request:

For the DOT11_BYTE_ARRAY structure, set the 
        <b>uNumOfBytes</b> and 
        <b>uTotalNumOfBytes</b> members to the total number of entries in the 
        <b>ucBuffer</b> array.

For the 
        <i>OidRequest</i> parameter, set the 
        <b>BytesNeeded</b> member to zero and the 
        <b>BytesWritten</b> member to the length, in bytes, of the entire DOT11_BYTE_ARRAY structure. The
        miniport driver must also copy the entire DOT11_BYTE_ARRAY structure to the 
        <b>InformationBuffer</b> member.

Return NDIS_STATUS_SUCCESS from its 
        <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function.


## -see-also
<dl>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.oid_dot11_cipher_key_mapping_key">
   OID_DOT11_CIPHER_KEY_MAPPING_KEY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569360">OID_DOT11_ENUM_BSS_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_BYTE_ARRAY structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


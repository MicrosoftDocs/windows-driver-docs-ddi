---
UID: NS:bthddi._BRB_HEADER
title: "_BRB_HEADER"
author: windows-driver-content
description: The BRB_HEADER structure contains header information about a Bluetooth request block (BRB), including information about the BRB type that the Bluetooth driver stack uses to determine which kind of BRB type to process.
old-location: bltooth\brb_header.htm
old-project: bltooth
ms.assetid: c6da4cc9-294b-4cb7-80c8-8adee8d4c40b
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: BRB_HEADER, BRB_HEADER structure [Bluetooth Devices], _BRB_HEADER, bltooth.brb_header, bth_structs_69a21ba7-b425-45ec-bb2d-dd76a6cb8342.xml, bthddi/BRB_HEADER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bthddi.h
api_name:
-	BRB_HEADER
product: Windows
targetos: Windows
req.typenames: BRB_HEADER
---

# _BRB_HEADER structure


## -description


The BRB_HEADER structure contains header information about a Bluetooth request block (BRB), including
  information about the BRB type that the Bluetooth driver stack uses to determine which kind of BRB type to
  process.


## -syntax


````
typedef struct _BRB_HEADER {
  LIST_ENTRY ListEntry;
  ULONG      Length;
  USHORT     Version;
  USHORT     Type;
  ULONG      BthportFlags;
  NTSTATUS   Status;
  BTHSTATUS  BtStatus;
  PVOID      Context[BTHPORT_CONTEXT_SIZE];
  PVOID      ClientContext[BTHPORT_CONTEXT_SIZE];
  ULONG      Reserved[BTHPORT_RESERVED_FIELD_SIZE];
} BRB_HEADER;
````


## -struct-fields




### -field ListEntry

A LIST_ENTRY structure used by the current owner of the BRB to place the BRB in a queue.


### -field Length

The size, in bytes, of the BRB, including the BRB_HEADER structure. The 
     <a href="..\bthddi\nc-bthddi-pfnbth_allocate_brb.md">BthAllocateBrb</a>, 
     <a href="..\bthddi\nc-bthddi-pfnbth_initialize_brb.md">BthInitializeBrb</a> and 
     <a href="..\bthddi\nc-bthddi-pfnbth_reuse_brb.md">BthReuseBrb</a> functions automatically set this
     member.


### -field Version

For internal use only. Do not use.


### -field Type

The Bluetooth request block type. The 
     <a href="..\bthddi\nc-bthddi-pfnbth_allocate_brb.md">BthAllocateBrb</a>, 
     <a href="..\bthddi\nc-bthddi-pfnbth_initialize_brb.md">BthInitializeBrb</a> and 
     <a href="..\bthddi\nc-bthddi-pfnbth_reuse_brb.md">BthReuseBrb</a> functions automatically set this
     member.Possible values include:
     

<ul>
<li>BRB_HCI_GET_LOCAL_BD_ADDR</li>
<li>BRB_L2CA_REGISTER_SERVER</li>
<li>BRB_L2CA_UNREGISTER_SERVER</li>
<li>BRB_L2CA_OPEN_CHANNEL</li>
<li>BRB_L2CA_OPEN_CHANNEL_RESPONSE</li>
<li>BRB_L2CA_CLOSE_CHANNEL</li>
<li>BRB_L2CA_ACL_TRANSFER</li>
<li>BRB_L2CA_UPDATE_CHANNEL</li>
<li>BRB_L2CA_PING</li>
<li>BRB_REGISTER_PSM</li>
<li>BRB_UNREGISTER_PSM</li>
<li>BRB_SCO_REGISTER_SERVER</li>
<li>BRB_SCO_UNREGISTER_SERVER</li>
<li>BRB_SCO_OPEN_CHANNEL</li>
<li>BRB_SCO_OPEN_CHANNEL_RESPONSE</li>
<li>BRB_SCO_CLOSE_CHANNEL</li>
<li>BRB_SCO_TRANSFER</li>
<li>BRB_SCO_GET_CHANNEL_INFO</li>
<li>BRB_SCO_GET_SYSTEM_INFO</li>
<li>BRB_SCO_FLUSH_CHANNEL</li>
<li>BRB_ACL_GET_MODE</li>
<li>BRB_ACL_ENTER_ACTIVE_MODE</li>
<li>BRB_GET_DEVICE_INTERFACE_STRING</li>
</ul>

### -field BthportFlags

For internal use only. Do not use.


### -field Status

The NTSTATUS code that is passed when the BRB call completes.


### -field BtStatus

The Bluetooth status code (BTSTATUS) that corresponds to the NTSTATUS code that is passed in the 
     <b>Status</b> member. Possible values include:
     

<ul>
<li>BTH_ERROR_SUCCESS</li>
<li>BTH_ERROR_ACL_CONNECTION_ALREADY_EXISTS</li>
<li>BTH_ERROR_AUTHENTICATION_FAILURE</li>
<li>BTH_ERROR_COMMAND_DISALLOWED</li>
<li>BTH_ERROR_CONNECTION_TIMEOUT</li>
<li>BTH_ERROR_ENCRYPTION_MODE_NOT_ACCEPTABLE</li>
<li>BTH_ERROR_HARDWARE_FAILURE</li>
<li>BTH_ERROR_HOST_REJECTED_LIMITED_RESOURCES</li>
<li>BTH_ERROR_HOST_REJECTED_PERSONAL_DEVICE</li>
<li>BTH_ERROR_HOST_REJECTED_SECURITY_REASONS</li>
<li>BTH_ERROR_HOST_TIMEOUT</li>
<li>BTH_ERROR_INSTANT_PASSED</li>
<li>BTH_ERROR_INVALID_HCI_PARAMETER</li>
<li>BTH_ERROR_INVALID_LMP_PARAMETERS</li>
<li>BTH_ERROR_KEY_MISSING</li>
<li>BTH_ERROR_LMP_PDU_NOT_ALLOWED</li>
<li>BTH_ERROR_LMP_RESPONSE_TIMEOUT</li>
<li>BTH_ERROR_LMP_TRANSACTION_COLLISION</li>
<li>BTH_ERROR_LOCAL_HOST_TERMINATED_CONNECTION</li>
<li>BTH_ERROR_MAX_NUMBER_OF_CONNECTIONS</li>
<li>BTH_ERROR_MAX_NUMBER_OF_SCO_CONNECTIONS</li>
<li>BTH_ERROR_MEMORY_FULL</li>
<li>BTH_ERROR_NO_CONNECTION</li>
<li>BTH_ERROR_PAGE_TIMEOUT</li>
<li>BTH_ERROR_PAIRING_NOT_ALLOWED</li>
<li>BTH_ERROR_PAIRING_WITH_UNIT_KEY_NOT_SUPPORTED</li>
<li>BTH_ERROR_QOS_IS_NOT_SUPPORTED</li>
<li>BTH_ERROR_REMOTE_LOW_RESOURCES</li>
<li>BTH_ERROR_REMOTE_POWERING_OFF</li>
<li>BTH_ERROR_REMOTE_USER_ENDED_CONNECTION</li>
<li>BTH_ERROR_REPEATED_ATTEMPTS</li>
<li>BTH_ERROR_ROLE_CHANGE_NOT_ALLOWED</li>
<li>BTH_ERROR_SCO_AIRMODE_REJECTED</li>
<li>BTH_ERROR_SCO_INTERVAL_REJECTED</li>
<li>BTH_ERROR_SCO_OFFSET_REJECTED</li>
<li>BTH_ERROR_UKNOWN_LMP_PDU</li>
<li>BTH_ERROR_UNIT_KEY_NOT_USED</li>
<li>BTH_ERROR_UNKNOWN_HCI_COMMAND</li>
<li>BTH_ERROR_UNSPECIFIED_ERROR</li>
<li>BTH_ERROR_UNSUPPORTED_FEATURE_OR_PARAMETER</li>
<li>BTH_ERROR_UNSUPPORTED_LMP_PARM_VALUE</li>
<li>BTH_ERROR_UNSUPPORTED_REMOTE_FEATURE</li>
</ul>

### -field Context

For internal use only. Do not use.


### -field ClientContext

The client context that is associated with the BRB call. The caller can use this member to store a
     pointer or other information.


### -field Reserved

Reserved for future use. Do not use.


## -remarks



The BRB_HEADER structure contains common types of information about the specified BRB. The BRB_HEADER
    structure is used by all BRB structures that are used as the input buffer for 
    <a href="..\bthioctl\ni-bthioctl-ioctl_internal_bth_submit_brb.md">
    IOCTL_INTERNAL_BTH_SUBMIT_BRB</a> IOCTLs.

Profile drivers should not modify any of the members of the BRB_HEADER structure except 
    <b>ClientContext</b>.




## -see-also

<a href="..\bthddi\nc-bthddi-pfnbth_initialize_brb.md">BthInitializeBrb</a>



<a href="..\bthddi\nc-bthddi-pfnbth_allocate_brb.md">BthAllocateBrb</a>



<a href="..\bthddi\nc-bthddi-pfnbth_reuse_brb.md">BthReuseBrb</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20BRB_HEADER structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


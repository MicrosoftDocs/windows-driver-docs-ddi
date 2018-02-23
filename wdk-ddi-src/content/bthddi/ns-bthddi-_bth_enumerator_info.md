---
UID: NS:bthddi._BTH_ENUMERATOR_INFO
title: "_BTH_ENUMERATOR_INFO"
author: windows-driver-content
description: The BTH_ENUMERATOR_INFO structure contains information about an underlying device and the service that caused the Plug and Play (PnP) manager to load the profile driver.
old-location: bltooth\bth_enumerator_info.htm
old-project: bltooth
ms.assetid: e526d664-35cf-4738-9501-08298e90be1e
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PBTH_ENUMERATOR_INFO, BTH_ENUMERATOR_INFO structure [Bluetooth Devices], _BTH_ENUMERATOR_INFO, PBTH_ENUMERATOR_INFO, bthddi/BTH_ENUMERATOR_INFO, bltooth.bth_enumerator_info, PBTH_ENUMERATOR_INFO structure pointer [Bluetooth Devices], bthddi/PBTH_ENUMERATOR_INFO, bth_structs_7cdc888a-ed42-4988-917f-578522399179.xml, BTH_ENUMERATOR_INFO"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	bthddi.h
apiname:
-	BTH_ENUMERATOR_INFO
product: Windows
targetos: Windows
req.typenames: "*PBTH_ENUMERATOR_INFO, BTH_ENUMERATOR_INFO"
---

# _BTH_ENUMERATOR_INFO structure


## -description


The BTH_ENUMERATOR_INFO structure contains information about an underlying device and the service
  that caused the Plug and Play (PnP) manager to load the profile driver.


## -syntax


````
typedef struct _BTH_ENUMERATOR_INFO {
  ENUMERATOR_TYPE   EnumeratorType;
  ENUMERATOR_ACTION Action;
  ULONG             Port;
  ULONG             Flags;
  GUID              Guid;
  ULONG             InstanceId;
  WCHAR             InstanceIdStr[BTH_MAX_SERVICE_NAME_SIZE];
  USHORT            Vid;
  USHORT            Pid;
  USHORT            Mfg;
  USHORT            LocalMfg;
  USHORT            VidType;
  WCHAR             ServiceName[BTH_MAX_SERVICE_NAME_SIZE];
  CHAR              SdpPriLangServiceName[BTH_MAX_SERVICE_NAME_SIZE];
  WCHAR             DeviceString[BTH_MAX_SERVICE_NAME_SIZE];
} BTH_ENUMERATOR_INFO, *PBTH_ENUMERATOR_INFO;
````


## -struct-fields




### -field EnumeratorType

Reserved for use by the Bluetooth driver stack. Do not use.


### -field Action

Reserved for use by the Bluetooth driver stack. Do not use.


### -field Port

If the enumeration was caused by a connection request, this member contains the device's port
     number. Otherwise, this value is undefined. For a L2CAP connection request, the port number also
     identifies the Protocol/Service Multiplexer (PSM) that is being connected to. For an RFCOMM connection
     request, this is an RFCOMM data link connection identifier (DLCI).


### -field Flags

A flag that indicates the direction of the request. Possible values include:

<ul>
<li>BTH_ENUMERATORFL_INCOMING</li>
<li>BTH_ENUMERATORFL_OUTGOING</li>
<li>BTH_ENUMERATORFL_REENUM</li>
</ul>

### -field Guid


      The enumeration protocol or service class GUID. This value is usually obtained from the INF file
      that loaded the profile driver.
     


### -field InstanceId


      The instance ID of the protocol or service if the BTH_ENUMERATORFL_INCOMING flag is set.
     


### -field InstanceIdStr


      The instance ID of the protocol or service if the BTH_ENUMERATORFL_OUTGOING flag is set.
     


### -field Vid

The vendor ID of the remote device, which is obtained from SDP.


### -field Pid

The product ID of the remote device, which is obtained from SDP.


### -field Mfg

The manufacturer ID of the remote device, which is obtained from SDP.


### -field LocalMfg

The local radio manufacturer obtained from the HCI.


### -field VidType


      The remote device vendor ID type, which is obtained from SDP.
     


### -field ServiceName

The service name that is used for local services.


### -field SdpPriLangServiceName

The identifier used for remote services.


### -field DeviceString

The device string for the remote device.


## -remarks



The 
    <a href="..\bthioctl\ni-bthioctl-ioctl_internal_bthenum_get_enuminfo.md">
    IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO</a> call's output buffer contains the information about an
    underlying device and the service that caused the Plug and Play (PnP) manager to load the profile
    driver.




## -see-also

<a href="..\bthioctl\ni-bthioctl-ioctl_internal_bthenum_get_enuminfo.md">
   IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO</a>



<a href="..\bthioctl\ni-bthioctl-ioctl_internal_bthenum_get_enuminfo.md">
   IOCTL_INTERNAL_BTHENUM_GET_ENUMINFO</a>



<a href="https://msdn.microsoft.com/d5acaec6-7b3b-4dd9-8901-f96b4e49149f">ENUMERATOR_ACTION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20BTH_ENUMERATOR_INFO structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


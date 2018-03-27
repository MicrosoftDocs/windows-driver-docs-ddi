---
UID: NS:bthioctl._BTH_SDP_DISCONNECT
title: "_BTH_SDP_DISCONNECT"
author: windows-driver-content
description: The BTH_SDP_DISCONNECT structure contains input information about a connection handle to the remote SDP connection to terminate. This structure is passed as the input buffer of IOCTL_BTH_SDP_DISCONNECT.
old-location: bltooth\bth_sdp_disconnect.htm
old-project: bltooth
ms.assetid: d0466569-7c9d-40d2-8794-b1d877a52458
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PBTH_SDP_DISCONNECT, BTH_SDP_DISCONNECT, BTH_SDP_DISCONNECT structure [Bluetooth Devices], PBTH_SDP_DISCONNECT, PBTH_SDP_DISCONNECT structure pointer [Bluetooth Devices], _BTH_SDP_DISCONNECT, bltooth.bth_sdp_disconnect, bth_structs_049df802-3bad-49b0-b80e-f3b0a1579b72.xml, bthioctl/BTH_SDP_DISCONNECT, bthioctl/PBTH_SDP_DISCONNECT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthioctl.h
req.include-header: Bthioctl.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: "<= PASSIVE_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bthioctl.h
api_name:
-	BTH_SDP_DISCONNECT
product: Windows
targetos: Windows
req.typenames: BTH_SDP_DISCONNECT, *PBTH_SDP_DISCONNECT
---

# _BTH_SDP_DISCONNECT structure


## -description


The BTH_SDP_DISCONNECT structure contains input information about a connection handle to the remote
  SDP connection to terminate. This structure is passed as the input buffer of 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff536689">IOCTL_BTH_SDP_DISCONNECT</a>.


## -struct-fields




### -field HANDLE_SDP_FIELD_NAME

 




#### - hConnection

A handle for the SDP connection on the remote server to terminate. This should be a value returned
     in the 
     <b>hConnection</b> member of the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536648">BTH_SDP_CONNECT</a> structure of a previous call
     to 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536688">IOCTL_BTH_SDP_CONNECT</a>.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536648">BTH_SDP_CONNECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536688">IOCTL_BTH_SDP_CONNECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536689">IOCTL_BTH_SDP_DISCONNECT</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20BTH_SDP_DISCONNECT structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


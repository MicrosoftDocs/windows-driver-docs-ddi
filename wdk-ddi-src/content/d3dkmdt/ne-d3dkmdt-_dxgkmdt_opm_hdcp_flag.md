---
UID: NE:d3dkmdt._DXGKMDT_OPM_HDCP_FLAG
title: "_DXGKMDT_OPM_HDCP_FLAG"
author: windows-driver-content
description: The DXGKMDT_OPM_HDCP_FLAG enumeration identifies whether a protected output's physical connector is connected to a High-bandwidth Digital Content Protection (HDCP) repeater.
old-location: display\dxgkmdt_opm_hdcp_flag.htm
old-project: display
ms.assetid: 479a5913-eee6-4f39-9e51-d04708658bc2
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGKMDT_OPM_HDCP_FLAG, DXGKMDT_OPM_HDCP_FLAG enumeration [Display Devices], DXGKMDT_OPM_HDCP_FLAG_NONE, DXGKMDT_OPM_HDCP_FLAG_REPEATER, DmEnums_4969beac-7f4f-4bef-bd67-65599816c9ee.xml, _DXGKMDT_OPM_HDCP_FLAG, d3dkmdt/DXGKMDT_OPM_HDCP_FLAG, d3dkmdt/DXGKMDT_OPM_HDCP_FLAG_NONE, d3dkmdt/DXGKMDT_OPM_HDCP_FLAG_REPEATER, display.dxgkmdt_opm_hdcp_flag
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmdt.h
apiname:
-	DXGKMDT_OPM_HDCP_FLAG
product: Windows
targetos: Windows
req.typenames: DXGKMDT_OPM_HDCP_FLAG
---

# _DXGKMDT_OPM_HDCP_FLAG enumeration


## -description


The DXGKMDT_OPM_HDCP_FLAG enumeration identifies whether a protected output's physical connector is connected to a High-bandwidth Digital Content Protection (HDCP) repeater. 


## -syntax


````
typedef enum _DXGKMDT_OPM_HDCP_FLAG { 
  DXGKMDT_OPM_HDCP_FLAG_NONE      = 0x00,
  DXGKMDT_OPM_HDCP_FLAG_REPEATER  = 0x01
} DXGKMDT_OPM_HDCP_FLAG;
````


## -enum-fields




### -field DXGKMDT_OPM_HDCP_FLAG_NONE

Indicates that no HDCP flags are set. Therefore, the protected output's physical connector is not connected to an HDCP repeater. 


### -field DXGKMDT_OPM_HDCP_FLAG_REPEATER

Indicates that the protected output's physical connector is connected to an HDCP repeater. 


## -remarks



The DXGKMDT_OPM_HDCP_FLAG enumeration is used only if a protected output has Certified Output Protection Protocol (COPP) semantics. 

An HDCP repeater is a device that allows multiple monitors to display the video signal from a protected output's physical connector. For example, if a user connected an HDCP repeater from a graphics adapter's Digital Video Interface (DVI) connector to a TV monitor and computer monitor, both monitors would display the same picture. For more information about HDCP repeaters, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=38728">HDCP Specification Revision 1.1</a>. 




## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_connected_hdcp_device_information.md">DXGKMDT_OPM_CONNECTED_HDCP_DEVICE_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKMDT_OPM_HDCP_FLAG enumeration%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


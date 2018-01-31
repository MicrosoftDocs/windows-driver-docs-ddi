---
UID: NE:iddcx.IDDCX_TRANSMISSION_TYPE
title: IDDCX_TRANSMISSION_TYPE
author: windows-driver-content
description: Enum used to indicate the link type for transmission of the video data.
old-location: display\iddcx_transmission_type.htm
old-project: display
ms.assetid: fc0a6c04-a348-470d-b8eb-9564f2ff7ef9
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: iddcx/IDDCX_TRANSMISSION_TYPE_WIRED_OTHER, IDDCX_TRANSMISSION_TYPE_WIRED_MIRACAST, iddcx/IDDCX_TRANSMISSION_TYPE_WIRELESS_MAUSB, iddcx/IDDCX_TRANSMISSION_TYPE_OTHER, IDDCX_TRANSMISSION_TYPE enumeration [Display Devices], IDDCX_TRANSMISSION_TYPE, iddcx/IDDCX_TRANSMISSION_TYPE_WIRED_MIRACAST, IDDCX_TRANSMISSION_TYPE_WIRELESS_MIRACAST, iddcx/IDDCX_TRANSMISSION_TYPE_WIRELESS_USB_OTHER, iddcx/IDDCX_TRANSMISSION_TYPE_WIRED_USB, IDDCX_TRANSMISSION_TYPE_WIRELESS_USB_OTHER, IDDCX_TRANSMISSION_TYPE_WIRELESS_MAUSB, iddcx/IDDCX_TRANSMISSION_TYPE_UNINITIALIZED, IDDCX_TRANSMISSION_TYPE_WIRELESS_OTHER, iddcx/IDDCX_TRANSMISSION_TYPE_WIRELESS_MIRACAST, IDDCX_TRANSMISSION_TYPE_OTHER, IDDCX_TRANSMISSION_TYPE_UNINITIALIZED, iddcx/IDDCX_TRANSMISSION_TYPE, IDDCX_TRANSMISSION_TYPE_WIRED_USB, IDDCX_TRANSMISSION_TYPE_WIRELESS_WIFI_OTHER, iddcx/IDDCX_TRANSMISSION_TYPE_WIRELESS_WIFI_OTHER, iddcx/IDDCX_TRANSMISSION_TYPE_WIRELESS_OTHER, IDDCX_TRANSMISSION_TYPE_WIRED_OTHER, display.iddcx_transmission_type
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: iddcx.h
req.include-header: 
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
req.irql: "_requires_same_"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	iddcx.h
apiname:
-	IDDCX_TRANSMISSION_TYPE
product: Windows
targetos: Windows
req.typenames: 
---

# IDDCX_TRANSMISSION_TYPE enumeration


## -description



Enum used to indicate the link type for transmission of the video data
                


## -syntax


````
typedef enum _IDDCX_TRANSMISSION_TYPE { 
  IDDCX_TRANSMISSION_TYPE_UNINITIALIZED        = 0,
  IDDCX_TRANSMISSION_TYPE_WIRED_USB            = 0x1,
  IDDCX_TRANSMISSION_TYPE_WIRED_MIRACAST       = 0x2,
  IDDCX_TRANSMISSION_TYPE_WIRED_OTHER          = 0x3,
  IDDCX_TRANSMISSION_TYPE_WIRELESS_MAUSB       = 0x4,
  IDDCX_TRANSMISSION_TYPE_WIRELESS_USB_OTHER   = 0x5,
  IDDCX_TRANSMISSION_TYPE_WIRELESS_WIFI_OTHER  = 0x6,
  IDDCX_TRANSMISSION_TYPE_WIRELESS_MIRACAST    = 0x7,
  IDDCX_TRANSMISSION_TYPE_WIRELESS_OTHER       = 0x8,
  IDDCX_TRANSMISSION_TYPE_OTHER                = 0xFFFFFFFF
} IDDCX_TRANSMISSION_TYPE;
````


## -enum-fields




#### - IDDCX_TRANSMISSION_TYPE_UNINITIALIZED


                        
                    Indicates that an <b>IDDCX_TRANSMISSION_TYPE</b> variable has not yet been assigned a meaningful value.


#### - IDDCX_TRANSMISSION_TYPE_WIRED_USB


                        Video data is being transmitted over wired USB
                    


#### - IDDCX_TRANSMISSION_TYPE_WIRED_MIRACAST


                        Video data is being transmitted over wired Miracast link
                    


#### - IDDCX_TRANSMISSION_TYPE_WIRED_OTHER


                        Video data is being transmitted over a wired connect not already described
                    


#### - IDDCX_TRANSMISSION_TYPE_WIRELESS_MAUSB


                        Video data is being transmitted over wireless MA-USB
                    


#### - IDDCX_TRANSMISSION_TYPE_WIRELESS_USB_OTHER


                        Video data is being transmitted over wireless network not using MA-USB but the device is enumerated on the USB bus
                    


#### - IDDCX_TRANSMISSION_TYPE_WIRELESS_WIFI_OTHER


                        Video data is being transmitted over a WiFi wireless network
                    


#### - IDDCX_TRANSMISSION_TYPE_WIRELESS_MIRACAST


                        Video data is being transmitted over wireless Miracast link
                    


#### - IDDCX_TRANSMISSION_TYPE_WIRELESS_OTHER


                        Video data is being transmitted over a non-WiFi wireless network not described above
                    


#### - IDDCX_TRANSMISSION_TYPE_OTHER


                        Video data is being transmitted over a link type that is not covered by the above defines
                    


### -field UINT




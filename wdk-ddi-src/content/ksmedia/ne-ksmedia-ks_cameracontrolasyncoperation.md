---
UID: NE:ksmedia.KS_CameraControlAsyncOperation
title: KS_CameraControlAsyncOperation
author: windows-driver-content
description: Defines notifications that the driver uses to start and stop an asynchronous camera operation, including setting the flash, the image pin control properties, the region of interest in the image, or video stabilization.
old-location: stream\ks_cameracontrolasyncoperation.htm
old-project: stream
ms.assetid: 0ca676d9-5047-451a-abbb-2692cc2d69f6
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, A, C, K, KS_CAMERACONTROL_ASYNC_RESET, KS_CAMERACONTROL_ASYNC_START, KS_CAMERACONTROL_ASYNC_STOP, KS_CameraControlAsyncOperation, KS_CameraControlAsyncOperation enumeration [Streaming Media Devices], O, S, _, a, c, e, i, ksmedia/KS_CAMERACONTROL_ASYNC_RESET, ksmedia/KS_CAMERACONTROL_ASYNC_START, ksmedia/KS_CAMERACONTROL_ASYNC_STOP, ksmedia/KS_CameraControlAsyncOperation, l, m, n, o, p, r, s, stream.ks_cameracontrolasyncoperation, t, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ksmedia.h
apiname:
-	KS_CameraControlAsyncOperation
product: Windows
targetos: Windows
req.typenames: KS_CameraControlAsyncOperation
---

# KS_CameraControlAsyncOperation enumeration


## -description


Defines notifications that the driver uses to start and stop an asynchronous camera operation, including setting the flash, the image pin control properties, the region of interest in the image, or video stabilization.


## -syntax


````
typedef enum  { 
  KS_CAMERACONTROL_ASYNC_START  = 0x0001,
  KS_CAMERACONTROL_ASYNC_STOP   = 0x0002,
  KS_CAMERACONTROL_ASYNC_RESET  = 0x0003
} KS_CameraControlAsyncOperation;
````


## -enum-fields




### -field KS_CAMERACONTROL_ASYNC_START

Initiate an asynchronous camera control operation.


### -field KS_CAMERACONTROL_ASYNC_STOP

Stop the requested asynchronous camera control operation and maintain current camera control settings, including the lens focus.


### -field KS_CAMERACONTROL_ASYNC_RESET

Stop the requested asynchronous camera control operation and reset the lens focus to infinity.


## -remarks



For more information, see <a href="..\ksmedia\ns-ksmedia-ksproperty_cameracontrol_s_ex.md">KSPROPERTY_CAMERACONTROL_S_EX</a>.




## -see-also

<a href="..\ksmedia\ns-ksmedia-ksproperty_cameracontrol_s_ex.md">KSPROPERTY_CAMERACONTROL_S_EX</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_CameraControlAsyncOperation enumeration%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


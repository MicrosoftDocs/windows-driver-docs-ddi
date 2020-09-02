---
UID: NE:ksmedia.__unnamed_enum_76
title: KS_CameraControlAsyncOperation (ksmedia.h)
description: Defines notifications that the driver uses to start and stop an asynchronous camera operation, including setting the flash, the image pin control properties, the region of interest in the image, or video stabilization.
old-location: stream\ks_cameracontrolasyncoperation.htm
tech.root: stream
ms.assetid: 0ca676d9-5047-451a-abbb-2692cc2d69f6
ms.date: 04/23/2018
keywords: ["KS_CameraControlAsyncOperation enumeration"]
ms.keywords: KS_CAMERACONTROL_ASYNC_RESET, KS_CAMERACONTROL_ASYNC_START, KS_CAMERACONTROL_ASYNC_STOP, KS_CameraControlAsyncOperation, KS_CameraControlAsyncOperation enumeration [Streaming Media Devices], ksmedia/KS_CAMERACONTROL_ASYNC_RESET, ksmedia/KS_CAMERACONTROL_ASYNC_START, ksmedia/KS_CAMERACONTROL_ASYNC_STOP, ksmedia/KS_CameraControlAsyncOperation, stream.ks_cameracontrolasyncoperation
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
targetos: Windows
req.typenames: KS_CameraControlAsyncOperation
f1_keywords:
 - KS_CameraControlAsyncOperation
 - ksmedia/KS_CameraControlAsyncOperation
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ksmedia.h
api_name:
 - KS_CameraControlAsyncOperation
---

# KS_CameraControlAsyncOperation enumeration


## -description

Defines notifications that the driver uses to start and stop an asynchronous camera operation, including setting the flash, the image pin control properties, the region of interest in the image, or video stabilization.

## -enum-fields

### -field KS_CAMERACONTROL_ASYNC_START

Initiate an asynchronous camera control operation.

### -field KS_CAMERACONTROL_ASYNC_STOP

Stop the requested asynchronous camera control operation and maintain current camera control settings, including the lens focus.

### -field KS_CAMERACONTROL_ASYNC_RESET

Stop the requested asynchronous camera control operation and reset the lens focus to infinity.

## -remarks

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_cameracontrol_s_ex">KSPROPERTY_CAMERACONTROL_S_EX</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_cameracontrol_s_ex">KSPROPERTY_CAMERACONTROL_S_EX</a>


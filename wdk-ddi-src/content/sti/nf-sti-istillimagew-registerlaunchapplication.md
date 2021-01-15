---
UID: NF:sti.IStillImageW.RegisterLaunchApplication
title: IStillImageW::RegisterLaunchApplication (sti.h)
description: The IStillImage::RegisterLaunchApplication method adds an application to the still image event monitor's list of push-model aware applications.
old-location: image\istillimage_registerlaunchapplication.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["IStillImageW::RegisterLaunchApplication"]
ms.keywords: IStillImageW interface [Imaging Devices],RegisterLaunchApplication method, IStillImageW.RegisterLaunchApplication, IStillImageW::RegisterLaunchApplication, RegisterLaunchApplication, RegisterLaunchApplication method [Imaging Devices], RegisterLaunchApplication method [Imaging Devices],IStillImageW interface, image.istillimage_registerlaunchapplication, sti/IStillImageW::RegisterLaunchApplication, stifnc_606c7e24-38e2-450e-a9d5-3d7018ccf9b9.xml
req.header: sti.h
req.include-header: Sti.h
req.target-type: Desktop
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IStillImageW::RegisterLaunchApplication
 - sti/IStillImageW::RegisterLaunchApplication
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - sti.h
api_name:
 - IStillImageW::RegisterLaunchApplication
---

# IStillImageW::RegisterLaunchApplication


## -description

The <b>IStillImage::RegisterLaunchApplication</b> method adds an application to the still image event monitor's list of push-model aware applications.

## -parameters

### -param pwszAppName 

[in]
Caller-supplied pointer to a string representing the application's "short name", which Scanners and Cameras Control Panel's property sheet will display.

### -param pwszCommandLine 

[in]
Caller-supplied pointer to a string representing the command line required to start the application, including the full path to the application's executable file. The current path can be obtained by calling <b>GetModuleFileName</b> (described in the Microsoft Windows SDK documentation). For more information, see the following <b>Remarks</b> section.

## -returns

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## -remarks

An application (or the application's installer) must call <b>IStillImage::RegisterLaunchApplication</b> so the still image event monitor will know of its existence. Users associate <a href="/windows-hardware/drivers/image/still-image-device-events">Still Image Device Events</a> with registered applications by using Control Panel's property sheet interface. After a user has associated a device event with the application, the event monitor will start the application when the event occurs.

The method writes the application's load path in the registry. Therefore, the method should be called each time the application runs, because the user might have moved the file and <b>GetModuleFileName</b> always returns the current file location.

You can include command arguments in the application's command line. When starting a registered application, the event monitor appends the following two arguments to the command line:

<table>
<tr>
<td>
<b>/StiDevice:</b><i>InternalDeviceName</i>

</td>
<td>
<i>InternalDeviceName</i> is the internal device name of the device for which the application is being started.

</td>
</tr>
<tr>
<td>
<b>/StiEvent:</b><i>EventGUID</i>

</td>
<td>
<i>EventGUID</i> is the string representation of the GUID for the device event that has occurred.

</td>
</tr>
</table>
 

The application can obtain the values specified for these arguments by calling <a href="/previous-versions/windows/hardware/drivers/ff543790(v=vs.85)">IStillImage::GetSTILaunchInformation</a>.

Before calling <b>IStillImage::RegisterLaunchApplication</b>, clients of the <b>IStillImage</b> COM interface must call <a href="/previous-versions/windows/hardware/drivers/ff543804(v=vs.85)">IStillImage::StiCreateInstance</a> to obtain an <b>IStillImage</b> interface pointer.


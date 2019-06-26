---
UID: NF:portabledeviceclassextension.IPortableDeviceClassExtension.ProcessLibraryMessage
title: IPortableDeviceClassExtension::ProcessLibraryMessage (portabledeviceclassextension.h)
description: The ProcessLibraryMessage interface processes class library-specific messages and commands.
old-location: wpddk\iportabledeviceclassextension_processlibrarymessage.htm
tech.root: wpd_dk
ms.assetid: b9e5f556-de9e-465f-a02f-ff4c1cb414b3
ms.date: 02/15/2018
ms.keywords: IPortableDeviceClassExtension interface,ProcessLibraryMessage method, IPortableDeviceClassExtension.ProcessLibraryMessage, IPortableDeviceClassExtension::ProcessLibraryMessage, IPortableDeviceClassExtensionProcessLibraryMessage, ProcessLibraryMessage, ProcessLibraryMessage method, ProcessLibraryMessage method,IPortableDeviceClassExtension interface, portabledeviceclassextension/IPortableDeviceClassExtension::ProcessLibraryMessage, wpddk.iportabledeviceclassextension_processlibrarymessage
ms.topic: method
req.header: portabledeviceclassextension.h
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- PortableDeviceClassExtension.h
api_name:
- IPortableDeviceClassExtension.ProcessLibraryMessage
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDeviceClassExtension::ProcessLibraryMessage


## -description



The ProcessLibraryMessage interface processes class library-specific messages and commands. A WPD driver calls this method whenever it needs to update device information (on its devnode), for example the device friendly name, enable or disable device service Plug and Play (PnP) interfaces, and so on.




## -parameters




### -param pParams [in]

An IPortableDeviceValues object that contains the library-specific command parameters. Supported commands (and associated parameters and results) are WPD_COMMAND_CLASS_EXTENSION_WRITE_DEVICE_INFORMATION, WPD_COMMAND_CLASS_EXTENSION_REGISTER_SERVICE_INTERFACES, and WPD_COMMAND_CLASS_EXTENSION_UNREGISTER_SERVICE_INTERFACES.


### -param pResults [out]

An IPortableDeviceValues object that contains the library-specific command results.


## -returns



The method returns an <b>HRESULT</b>. The possible return values are shown in the following table.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_POINTER</b></dt>
</dl>
</td>
<td width="60%">
A required pointer argument was <b>NULL</b>.

</td>
</tr>
</table>
 




## -remarks



To be supplied.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portabledeviceclassextension/nn-portabledeviceclassextension-iportabledeviceclassextension">IPortableDeviceClassExtension Interface</a>
 

 


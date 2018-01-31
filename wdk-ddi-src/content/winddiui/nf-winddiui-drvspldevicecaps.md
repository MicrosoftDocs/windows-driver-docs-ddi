---
UID: NF:winddiui.DrvSplDeviceCaps
title: DrvSplDeviceCaps function
author: windows-driver-content
description: A printer interface DLL's DrvSplDeviceCaps function queries a printer for its capabilities.
old-location: print\drvspldevicecaps.htm
old-project: print
ms.assetid: 3d129a30-a892-4f4d-b8e3-f277d97980f4
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: DrvSplDeviceCaps function [Print Devices], print.drvspldevicecaps, winddiui/DrvSplDeviceCaps, print_interface-graphics_8c345fd4-e513-44ff-94b0-2f035db6a022.xml, DrvSplDeviceCaps
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winddiui.h
req.include-header: Winddiui.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	winddiui.h
apiname:
-	DrvSplDeviceCaps
product: Windows
targetos: Windows
req.typenames: WINBIO_VERSION, *PWINBIO_VERSION
req.product: Windows 10 or later.
---

# DrvSplDeviceCaps function


## -description


A printer interface DLL's <b>DrvSplDeviceCaps</b> function queries a printer for its capabilities.


## -syntax


````
DWORD DrvSplDeviceCaps(
            HANDLE   hPrinter,
  _In_      PWSTR    pwDeviceName,
            WORD     DeviceCap,
  _Out_opt_ PVOID    pvOutput,
            DWORD    cchBuf,
  _In_opt_  PDEVMODE pDM
);
````


## -parameters




#### - hPrinter

Caller-supplied handle to the printer.


### -param pszDeviceName

TBD


### -param Capability

TBD


### -param pOutput

TBD


### -param cchBufSize

TBD


### -param pDevmode

TBD



#### - pwDeviceName [in]

Caller-supplied pointer to a Unicode string that contains the printer name.


#### - DeviceCap

Caller-supplied bit flag that indicates the capability to query for. (The flags are defined in header file wingdi.h.) This function is not required to support all of the DC_<i>XXX</i> flags, but it must support those listed in the following table.
<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
DC_MEDIAREADY

</td>
<td>
The <i>pvOutput</i> parameter points to a buffer that the function should fill with an array of string buffers, each 64 characters in length. Each array element should contain a NULL-terminated string representing a name for a paper form that is available for use. 

The function's return value should be the number of elements in the returned array.

If <i>pvOutput</i> is <b>NULL</b>, the function should just return the number of array elements required.

</td>
</tr>
<tr>
<td>
DC_PAPERNAMES

</td>
<td>
The <i>pvOutput</i> parameter points to a buffer that the function should fill with an array of string buffers, each 64 characters in length. Each array element should contain a NULL-terminated string representing a name for a paper form. 

The function's return value should be the number of elements in the returned array.

If <i>pvOutput</i> is <b>NULL</b>, the function should just return the number of array elements required.

</td>
</tr>
</table> 


#### - pvOutput [out, optional]

Caller-supplied pointer to a buffer that receives function-supplied information. The buffer's use depends on the value of  the <i>DeviceCap</i> parameter. The caller is responsible for allocating and freeing this buffer. 


#### - cchBuf

Caller-supplied size (in characters) of the buffer pointed to by the <i>pvOutput</i> parameter.


#### - pDM [in, optional]

Caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure that describes the current print job characteristics. If <b>NULL</b>, the function should use the driver's internal default DEVMODEW structure. 


## -returns


The return value depends on the <i>DeviceCap</i> parameter. If <i>DeviceCap</i> indicates a capability that the driver does not support, or if an error is encountered, the function should return GDI_ERROR.



## -remarks


The <b>DrvSplDeviceCaps</b> function is available in Microsoft Windows Server 2003 and later.

For descriptions of the DC_<i>XXX</i> flags, see <a href="..\winddiui\nf-winddiui-drvdevicecapabilities.md">DrvDeviceCapabilities</a>.

This function must be defined in the .def file as DrvSplDeviceCaps @ 254, because the spooler uses the ordinal number 254 to obtain the driver function pointer.



## -see-also

<a href="..\winddiui\nf-winddiui-drvdevicecapabilities.md">DrvDeviceCapabilities</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20DrvSplDeviceCaps function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


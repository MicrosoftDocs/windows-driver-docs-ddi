---
UID: NI:bthhfpddi.IOCTL_BTHHFP_DEVICE_GET_KSNODETYPES
title: IOCTL_BTHHFP_DEVICE_GET_KSNODETYPES
author: windows-driver-content
description: The IOCTL_BTHHFP_DEVICE_GET_KSNODETYPES IOCTL Gets the KSNODE types that best describe the Bluetooth device’s input and output.
old-location: audio\ioctl_bthhfp_device_get_ksnodetypes.htm
old-project: audio
ms.assetid: 6862B0FD-9A7B-40BF-8123-673EE443DE84
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: audio.ioctl_bthhfp_device_get_ksnodetypes, IOCTL_BTHHFP_DEVICE_GET_KSNODETYPES control code [Audio Devices], IOCTL_BTHHFP_DEVICE_GET_KSNODETYPES, bthhfpddi/IOCTL_BTHHFP_DEVICE_GET_KSNODETYPES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: bthhfpddi.h
req.include-header: 
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
-	Bthhfpddi.h
apiname:
-	IOCTL_BTHHFP_DEVICE_GET_KSNODETYPES
product: Windows
targetos: Windows
req.typenames: HFP_BYPASS_CODEC_ID_VERSION, *PHFP_BYPASS_CODEC_ID_VERSION
---

# IOCTL_BTHHFP_DEVICE_GET_KSNODETYPES IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The <b>IOCTL_BTHHFP_DEVICE_GET_KSNODETYPES</b> 
   IOCTL Gets the KSNODE types that best describe the Bluetooth device’s input and output.
<div class="alert"><b>Note</b>  This IOCTL has been deprecated for Windows 8.1, so you should use <a href="..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_descriptor.md">IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR</a> instead.</div><div> </div>

## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>struct
{
    GUID OutputType;
    GUID InputType;
}
</pre>
</td>
</tr>
</table></span></div>

#### -OutputType
 The KSNODE type for the output.


#### -InputType
 The KSNODE type for the intput.


### -output-buffer-length

The size of the specified structure.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

N/A


## -remarks



This request completes immediately.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn302027">Bluetooth HFP DDI IOCTLs</a>



<a href="..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_descriptor.md">IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IOCTL_BTHHFP_DEVICE_GET_KSNODETYPES control code%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


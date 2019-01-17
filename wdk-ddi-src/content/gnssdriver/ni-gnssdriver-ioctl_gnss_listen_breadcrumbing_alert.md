---
UID: NI:gnssdriver.IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT
title: IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT
description: The IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT control code is used to request alert information from GNSS_BREADCRUMBING_ALERT_DATA when the breadcrumbing buffer has reached a level at which OS read operations should be performed.
old-location: gnss\ioctl_gnss_listen_breadcrumbing_alert_.htm
tech.root: gnss
ms.assetid: 14D396B1-5F55-4902-8986-BD4CC5B2ACC4
ms.date: 02/15/2018
ms.keywords: IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT, IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT control, IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT control code [Sensor Devices], gnss.ioctl_gnss_listen_breadcrumbing_alert_, gnssdriver/IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT
ms.topic: ioctl
req.header: gnssdriver.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	gnssdriver.h
api_name:
-	IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT IOCTL


## -description


The <b>IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT </b> 
   control code is used to request alert information  from <a href="https://msdn.microsoft.com/library/windows/hardware/mt767987">GNSS_BREADCRUMBING_ALERT_DATA</a> when the breadcrumbing buffer has reached a level at which OS read
operations should be performed.


## -ioctlparameters




### -input-buffer

Pointer to the input buffer.


### -input-buffer-length

Size of the input buffer.


### -output-buffer

Pointer to the output buffer.


### -output-buffer-length

Size of the output buffer.


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks



<b>IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT</b> is defined as follows in the gnssdriver.h header file:

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>#define IOCTL_GNSS_LISTEN_BREADCRUMBING_ALERT \
    CTL_CODE( FILE_DEVICE_UNKNOWN, 0x072, METHOD_BUFFERED, FILE_ANY_ACCESS )</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548656">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548660">WdfIoTargetSendIoctlSynchronously</a>
 

 


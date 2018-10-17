---
UID: NI:gnssdriver.IOCTL_GNSS_RESPOND_NI
title: IOCTL_GNSS_RESPOND_NI
author: windows-driver-content
description: The IOCTL_GNSS_RESPOND_NI control code is used by the GNSS adapter to respond to an NI request that was asynchronously communicated to it by the GNSS driver through the resolution of an IOCTL_GNSS_LISTEN_NI request.
old-location: gnss\ioctl_gnss_respond_ni.htm
tech.root: gnss
ms.assetid: AEEB014C-653F-459A-A04A-6E0732E8E5B0
ms.date: 2/15/2018
ms.keywords: IOCTL_GNSS_RESPOND_NI, IOCTL_GNSS_RESPOND_NI control, IOCTL_GNSS_RESPOND_NI control code [Sensor Devices], gnss.ioctl_gnss_respond_ni, gnssdriver/IOCTL_GNSS_RESPOND_NI
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
-	IOCTL_GNSS_RESPOND_NI
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_GNSS_RESPOND_NI IOCTL


## -description


The <b>IOCTL_GNSS_RESPOND_NI</b> control code is used by the GNSS adapter to respond to an NI request that was asynchronously communicated to it by the GNSS driver through the resolution of an <a href="https://msdn.microsoft.com/library/windows/hardware/dn917738">IOCTL_GNSS_LISTEN_NI</a> request. 


## -ioctlparameters




### -input-buffer

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn925196">GNSS_NI_RESPONSE</a> structure.




### -input-buffer-length

Set to sizeof(GNSS_NI_RESPONSE).


### -output-buffer

Set to NULL.


### -output-buffer-length

Set to 0.


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks



The driver sets one of the following NTSTATUS values to indicate result.

<ul>
<li>
<b>STATUS_SUCCESS</b>, when the driver processed the users NI response information successfully.

</li>
<li>
<b>Failed</b>, when the driver does not process the users NI response information successfully.

</li>
<li>
<b>Ignored</b>, when the driver ignored the users NI response information.



</li>
</ul>
<h3><a id="GNSS_driver_notes"></a><a id="gnss_driver_notes"></a><a id="GNSS_DRIVER_NOTES"></a>GNSS driver notes</h3>
It is the GNSS driver’s responsibility to pass the user’s response, contained in the <b>GNSS_NI_RESPONSE</b> input structure to the NI. If the response is <b>GNSS_Ni_UserResponseTimeout</b>, the driver should determine the appropriate default response after time-out and send it to the SUPL server.






## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548656">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548660">WdfIoTargetSendIoctlSynchronously</a>
 

 


---
UID: NI:gnssdriver.IOCTL_GNSS_RESPOND_NI
title: IOCTL_GNSS_RESPOND_NI
author: windows-driver-content
description: The IOCTL_GNSS_RESPOND_NI control code is used by the GNSS adapter to respond to an NI request that was asynchronously communicated to it by the GNSS driver through the resolution of an IOCTL_GNSS_LISTEN_NI request.
old-location: sensors\ioctl_gnss_respond_ni.htm
old-project: sensors
ms.assetid: AEEB014C-653F-459A-A04A-6E0732E8E5B0
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: sensors.ioctl_gnss_respond_ni, IOCTL_GNSS_RESPOND_NI control code [Sensor Devices], IOCTL_GNSS_RESPOND_NI, gnssdriver/IOCTL_GNSS_RESPOND_NI
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	gnssdriver.h
apiname:
-	IOCTL_GNSS_RESPOND_NI
product: Windows
targetos: Windows
req.typenames: GNSS_SUPL_CERT_ACTION
---

# IOCTL_GNSS_RESPOND_NI IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The <b>IOCTL_GNSS_RESPOND_NI</b> control code is used by the GNSS adapter to respond to an NI request that was asynchronously communicated to it by the GNSS driver through the resolution of an <a href="..\gnssdriver\ni-gnssdriver-ioctl_gnss_listen_ni.md">IOCTL_GNSS_LISTEN_NI</a> request. 


## -ioctlparameters




### -input-buffer

A pointer to a <a href="..\gnssdriver\ns-gnssdriver-gnss_ni_response.md">GNSS_NI_RESPONSE</a> structure.




### -input-buffer-length

Set to sizeof(GNSS_NI_RESPONSE).


### -output-buffer

Set to NULL.


### -output-buffer-length

Set to 0.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



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
</ul><h3><a id="GNSS_driver_notes"></a><a id="gnss_driver_notes"></a><a id="GNSS_DRIVER_NOTES"></a>GNSS driver notes</h3>It is the GNSS driver’s responsibility to pass the user’s response, contained in the <b>GNSS_NI_RESPONSE</b> input structure to the NI. If the response is <b>GNSS_Ni_UserResponseTimeout</b>, the driver should determine the appropriate default response after time-out and send it to the SUPL server.





## -see-also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20IOCTL_GNSS_RESPOND_NI control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NI:gnssdriver.IOCTL_GNSS_LISTEN_NI
title: IOCTL_GNSS_LISTEN_NI
author: windows-driver-content
description: The IOCTL_GNSS_LISTEN_NI control code is used to start listening for a SUPL NI request.
old-location: sensors\ioctl_gnss_listen_ni.htm
old-project: sensors
ms.assetid: DDC85717-7CF7-421D-9521-09E272FFFCF0
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: sensors.ioctl_gnss_listen_ni, IOCTL_GNSS_LISTEN_NI control code [Sensor Devices], IOCTL_GNSS_LISTEN_NI, gnssdriver/IOCTL_GNSS_LISTEN_NI
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
-	IOCTL_GNSS_LISTEN_NI
product: Windows
targetos: Windows
req.typenames: GNSS_SUPL_CERT_ACTION
---

# IOCTL_GNSS_LISTEN_NI IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The <b>IOCTL_GNSS_LISTEN_NI</b> control code is used to start listening for a SUPL NI request.

This IOCTL effectively provides the GNSS driver with a pending I/O request that it can use to, through the overlapped structures GnssEvent member, convey the NI request to the adapter. The GnssEvent member is a <a href="..\gnssdriver\ns-gnssdriver-gnss_event.md">GNSS_EVENT</a> structure. The adapter ensures that this request is always pending and will issue a new request as soon as the pending one is resolved. When the I/O request is resolved the adapter will issue a corresponding <a href="..\gnssdriver\ni-gnssdriver-ioctl_gnss_respond_ni.md">IOCTL_GNSS_RESPOND_NI</a>.


## -ioctlparameters




### -input-buffer

Set to NULL. 




### -input-buffer-length

Set to 0.




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


The <b>EventType</b> must be set to <b>GNSS_Event_NI</b> and the <b>NiRequest</b> member filled in.
<h3><a id="GNSS_adapter_notes"></a><a id="gnss_adapter_notes"></a><a id="GNSS_ADAPTER_NOTES"></a>GNSS adapter notes</h3>The GNSS adapter ensures that this request is always pending, so that the driver can indicate there is a NI request.

When the driver completes the I/O call, the adapter issues another IOCTL to continue waiting for further NI requests. The adapter should issue the IOCTL immediately, even if the previous NI requests are held up due to user interaction.
<h3><a id="GNSS_driver_notes"></a><a id="gnss_driver_notes"></a><a id="GNSS_DRIVER_NOTES"></a>GNSS driver notes</h3>Whenever the GNSS driver gets a NI request from the SUPL/CP, it completes the I/O operation.

These certificates, which are specified by the mobile operator and configured via the SUPL configuration service provider, are needed for establishing connection with the H-SLP or E-SLP. The GNSS adapter only pushes the SUPL configuration, including the certificated, to the GNSS driver. It does not install the certificates in the Windows file system. This is because different IHVs may have different implementations of the SUPL client, and some may include implementation of their own TLS stack. The GNSS adapter is agnostic to any implementation details of the SUPL client. The GNSS driver can store the certificates in registry or disk or push them directly to the SUPL client based on their usage. The SUPL client will need to take care of installing/using the certificates as needed.



## -see-also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20IOCTL_GNSS_LISTEN_NI control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NF:wudfddi.IWDFDevice3.CreateInterrupt
title: IWDFDevice3::CreateInterrupt method
author: windows-driver-content
description: The CreateInterrupt method creates a framework interrupt object.
old-location: wdf\iwdfdevice3_createinterrupt.htm
old-project: wdf
ms.assetid: EE68BED8-5FDC-4590-8E95-B228F1DFD32D
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFDevice3, CreateInterrupt method, IWDFDevice3 interface, IWDFDevice3 interface, CreateInterrupt method, CreateInterrupt method, umdf.iwdfdevice3_createinterrupt, wdf.iwdfdevice3_createinterrupt, CreateInterrupt, IWDFDevice3::CreateInterrupt, wudfddi/IWDFDevice3::CreateInterrupt
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	COM
apilocation: 
-	WUDFx.dll
apiname: 
-	IWDFDevice3.CreateInterrupt
product: Windows
targetos: Windows
req.typenames: *PPOWER_ACTION, POWER_ACTION
req.product: Windows 10 or later.
---

# IWDFDevice3::CreateInterrupt method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CreateInterrupt</b> method creates a framework interrupt object.



## -syntax


````
HRESULT CreateInterrupt(
  [in]  PWUDF_INTERRUPT_CONFIG *Configuration,
  [out] IWDFInterrupt          **ppInterrupt
);
````


## -parameters




### -param Configuration [in]

A pointer to a <a href="..\wudfinterrupt\ns-wudfinterrupt-_wudf_interrupt_config.md">WUDF_INTERRUPT_CONFIG</a> structure that was initialized by a call to the <a href="..\wudfinterrupt\nf-wudfinterrupt-wudf_interrupt_config_init.md">WUDF_INTERRUPT_CONFIG_INIT</a> macro.


### -param ppInterrupt [out]

A pointer to a buffer that receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfinterrupt.md">IWDFInterrupt</a>  interface for the new interrupt object.


## -returns


The method returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.



## -remarks


Your driver must call <b>CreateInterrupt</b> one time for each interrupt vector that its device requires. If the device supports message-signaled interrupts (MSI), the driver must create an interrupt object for each message that the device can support. 

Drivers typically call the <b>CreateInterrupt</b> method from an <a href="https://msdn.microsoft.com/f2953b0d-6745-4804-bcda-47c7ddfb901f">OnDeviceAdd</a> callback function, but can also call this method from <a href="https://msdn.microsoft.com/830D706A-016C-4637-829F-2014AD1A1309">IPnpCallbackHardware2::OnPrepareHardware</a>.


After the Plug and Play (PnP) manager assigns system resources to the device, the framework stores information about the device's assigned interrupt resources in the interrupt objects that the driver has created. (Drivers that do not support Plug and Play cannot use interrupt objects.)


The system might not assign all the interrupt resources that a device can support. For example, a driver  creates eight interrupt objects for a device that is capable of supporting eight MSI messages. However, the system might assign only one message to the device. In that case, seven of the interrupt objects will be unused.


Typically, your driver should store interrupt-specific information, such as the copied contents of device interrupt registers, in the interrupt object's context space. A driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff560208">IWDFObject::AssignContext</a> to register a context and to request notification when the object becomes invalid.

UMDF supports level-triggered interrupts starting in Windows 8. If a driver running on an operating system earlier than  Windows 8 creates a level-triggered interrupt in <a href="https://msdn.microsoft.com/f2953b0d-6745-4804-bcda-47c7ddfb901f">OnDeviceAdd</a>, <b>CreateInterrupt</b> succeeds because the operating system has not yet assigned resources.  However, when the framework attempts to connect the interrupt later, the device fails to start.


For more information about handling interrupts in UMDF drivers, see <a href="https://msdn.microsoft.com/25D526CF-7C37-4D10-B099-352933F92F98">Accessing Hardware and Handling Interrupts</a>.



## -see-also

<a href="..\wudfinterrupt\ns-wudfinterrupt-_wudf_interrupt_config.md">WUDF_INTERRUPT_CONFIG</a>

<a href="..\wudfddi\nn-wudfddi-iwdfdevice3.md">IWDFDevice3</a>

<a href="..\wudfinterrupt\nf-wudfinterrupt-wudf_interrupt_config_init.md">WUDF_INTERRUPT_CONFIG_INIT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDevice3::CreateInterrupt method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


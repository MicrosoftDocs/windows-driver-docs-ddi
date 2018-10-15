---
UID: NF:wdfinstaller.WdfPreDeviceInstallEx
title: WdfPreDeviceInstallEx function
author: windows-driver-content
description: The co-installer's WdfPreDeviceInstallEx function performs any operations that the co-installer might require before a non-Plug and Play (PnP) driver's installer creates the driver's kernel-mode service.
old-location: wdf\wdfpredeviceinstallex.htm
tech.root: wdf
ms.assetid: 99de930a-0d01-4177-b0d9-4692cc570303
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFCoinstallerRef_0142df49-f344-47f7-bcd1-6e37e5d439fe.xml, WdfPreDeviceInstallEx, WdfPreDeviceInstallEx function, kmdf.wdfpredeviceinstallex, wdf.wdfpredeviceinstallex, wdfinstaller/WdfPreDeviceInstallEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfinstaller.h
req.include-header: Wdfinstaller.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: N/A (Exported by the KMDF co-installer library. For information about the co-installer library's filename, see Using the KMDF Co-installer.)
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	N/A
-	N/A.dll
api_name:
-	WdfPreDeviceInstallEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfPreDeviceInstallEx function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The co-installer's <b>WdfPreDeviceInstallEx</b> function performs any operations that the co-installer might require before a non-Plug and Play (PnP) driver's installer creates the driver's kernel-mode service. 


## -parameters




### -param InfPath [in]

A pointer to a null-terminated wide-character string that contains the directory path to the driver's INF file. The driver's installer can obtain this string by calling <b>GetCurrentDirectory</b>, which is described in the Microsoft Windows SDK.


### -param InfSectionName [in, optional]

A pointer to a null-terminated wide-character string that contains the <i>Wdf-install-section</i> name in the driver's INF file. For more information about this name, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/installing-the-framework-s-co-installer">Using the KMDF Co-installer</a>. If this pointer is <b>NULL</b>, the co-installer uses <b>WdfSection</b> for the name.


### -param ClientOptions [in]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff551241">WDF_COINSTALLER_INSTALL_OPTIONS</a>-typed structure that contains driver-specified installation options. 


## -returns



<b>WdfPreDeviceInstallEx</b> returns ERROR_SUCCESS if the operation succeeds. Otherwise, the function returns one of the additional ERROR_<i>XXX</i> values that are defined in <i>Winerror.h</i>.




## -remarks



The installer for the framework-based drivers of a non-PnP device must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548835">WdfPreDeviceInstall</a> or <b>WdfPreDeviceInstallEx</b> before the installer calls <b>CreateService</b>.

To obtain the address of the co-installer's <b>WdfPreDeviceInstallEx</b> function, the installer must call <b>GetProcAddress</b> after the installer has called <b>LoadLibrary</b> to load the co-installer.

If the co-installer determines that the computer must be restarted to complete the driver installation (typically because an older version of the framework was previously installed), the <b>WdfPreDeviceInstallEx</b> function enables you to control when or whether the user is prompted to restart the computer, as follows:

<ul>
<li>
If the installer sets the <i>ShowRebootPrompt</i> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551241">WDF_COINSTALLER_INSTALL_OPTIONS</a> structure to <b>TRUE</b>, <b>WdfPreDeviceInstallEx</b> informs the PnP manager that the computer must be restarted, and the PnP manager prompts the user that a restart is necessary. Setting the <i>ShowRebootPrompt</i> member to <b>TRUE</b> is equivalent to calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff548835">WdfPreDeviceInstall</a>.

</li>
<li>
If the installer sets the <i>ShowRebootPrompt</i> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551241">WDF_COINSTALLER_INSTALL_OPTIONS</a> structure to <b>FALSE</b>, <b>WdfPreDeviceInstallEx</b> does not inform the PnP manager that a restart is necessary. Instead, the function returns <b>ERROR_SUCCESS_REBOOT_REQUIRED</b>. Your installer can determine when or whether to restart the computer, 

</li>
</ul>
For more information about the <b>WdfPreDeviceInstallEx</b> function and installers for framework-based drivers of non-PnP devices, see <a href="https://msdn.microsoft.com/99676d85-feb2-482c-a91b-cfc48be5904c">Installing a Non-PnP Driver</a>. For more information about <b>CreateService</b>, <b>GetProcAddress</b>, and <b>LoadLibrary</b>, see the Microsoft Windows SDK documentation.


#### Examples

For a code example that uses the <b>WdfPreDeviceInstallEx</b> function, see the installer for the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/sample-kmdf-drivers">NONPNP</a> sample.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548829">WdfPostDeviceInstall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548835">WdfPreDeviceInstall</a>
 

 


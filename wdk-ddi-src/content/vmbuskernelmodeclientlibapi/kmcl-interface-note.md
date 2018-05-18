> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. 
>
> To access the KMCL interface, allocate a **KMCL_CLIENT_INTERFACE_V1** structure to receive the interface, then call either [**WdfFdoQueryForInterface**](../wdffdo/nf-wdffdo-wdffdoqueryforinterface.md) or [**WdfIoTargetQueryForInterface**](../wdfiotarget/nf-wdfiotarget-wdfiotargetqueryforinterface.md) with these parameters:
> 
> - *InterfaceType* parameter: **KMCL_CLIENT_INTERFACE_TYPE**
> - *Size* parameter: `sizeof(KMCL_CLIENT_INTERFACE_V1)`
> - *Version* parameter set to **KMCL_CLIENT_INTERFACE_VERSION_LATEST** 
>
> If the interface query function succeeds, the **KMCL_CLIENT_INTERFACE_V1** structure contains function pointers for the VMBus KMCL functions that you can use to call them.
>
> For more information about driver-defined interfaces, see [Using Driver-Defined Interfaces](https://docs.microsoft.com/windows-hardware/drivers/wdf/using-driver-defined-interfaces).
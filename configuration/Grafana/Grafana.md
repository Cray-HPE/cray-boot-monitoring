# Boot Monitoring Grafana Dashboard

- [Boot DHCP Error Dashboard](#boot-dhcp-error-dashboard)
- [Boot Device Error Dashboard](#boot-device-error-dashboard)
- [Boot Mixed Error Dashboard](#boot-mixed-error-dashboard)
- [Boot PXE error Dashboard](#boot-pxe-error-dashboard)
- [Known Issues Message Frequency Dashboard](#known-issues-message-frequency-dashboard)
- [CSM Install Progress Dashboard](#csm-install-progress-dashboard)


## Boot DHCP Error Dashboard

This dashboard contains different DHCP errors around boot during install such as failure count for dhcp server, dhcp dracut-initqueue total count for unsend packets, discovery and interface failed.

## Boot Device Error Dashboard

This dashboard has errors related to USB device around boot such as number of times device is disconnected, port1 errors and error message regarding errors. 

## Boot Mixed Error Dashboard

This dashboard contains errors or failure messages from different environment such as errors related to DNS and I/O error.

## Boot PXE error Dashboard  

This dashboard capture the errors from Preboot Execution Environment or PXE white installation. It has visualizations such as total count of server response timeout, remote boot cancelled, unexpected network error, etc.

## Known Issues Message Frequency Dashboard

This dashboard maintains the frequency of known issues that is seen around boot like pool allocation failed count, pcieport DPC error, etc.

## CSM Install Progress Dashboard

This dashboard keeps track of different errors, failure, unknown and warning message counts in the installation process of CSM environments such as total errors count, total failure count, total warning count, etc.

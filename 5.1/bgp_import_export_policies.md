# Introduction
We need to add sub-cluster extended community called origin-sub-cluster extended community to all routes originated within a sub-cluster (similar to origin-vn) by encoding sub-cluster-id as the value field inside the extended-community
For this we need to get a type reserved from IANA.

Apply import policy to virtual-network to secondary routes too, but only if self sub-cluster id does not match what is associated with the route.

If there is no sub-cluster extended-community associated with the route, then do apply the policy for secondary routes. This is required to solve Orange's immediate use case where there may not be any sub-cluster configured.

If route is service-chain route, then do not apply virtual-network policy (primary or secondary). Instead, apply service-chain policy to only service-chain primary routes.

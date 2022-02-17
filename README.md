# ingress-yaml-example

## Istio:

```
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: mn-ingress-istio
  annotations:
          kubernetes.io/ingress.class: istio
spec:
  rules:
    - host: hello-world-istio.info
      http:
        paths:
          - path: /
            pathType: Prefix
            backend:
              service:
                name: nginx
                port:
                  number: 80

```

nginx:

~~~
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: mn-ingress
  annotations:
          kubernetes.io/ingress.class: "nginx"
spec:
  rules:
    - host: hello-world.info
      http:
        paths:
          - path: /
            pathType: Prefix
            backend:
              service:
                name: nginx
                port:
                  number: 80

~~~

# 🏆 Lost & Found Portal - 1er Lugar AWS re/Start Hackathon

## Equipo (LabCraft)
- Nicolas Murcia
- Alonzo Loyaga
- Steven Relayza

> Plataforma *Serverless* e inteligente para la gestión y recuperación de objetos perdidos en centros comerciales utilizando IA Generativa y visión artificial.

## Descripción del Proyecto
La gestión tradicional de objetos perdidos presenta deficiencias operativas, procesos manuales y riesgos de entrega a personas equivocadas. **Lost & Found** resuelve este problema automatizando los reportes y detectando coincidencias entre objetos extraviados y hallados mediante **Amazon Bedrock (Nova Lite)**. Además, incorpora validación digital con códigos alfanuméricos únicos para garantizar la trazabilidad en la devolución.

## Arquitectura en AWS
El proyecto fue construido siguiendo los pilares del AWS Well-Architected Framework, utilizando un modelo 100% Pay-as-you-go.

- **Frontend y Distribución:** Amazon S3, Amazon CloudFront
- **Autenticación y Seguridad:** Amazon Cognito, AWS IAM
- **API y Orquestación:** Amazon API Gateway, AWS Lambda
- **Base de Datos y Almacenamiento:** Amazon DynamoDB, Amazon S3
- **Inteligencia Artificial Multimodal:** Amazon Bedrock (Nova Lite)
- **Notificaciones y Auditoría:** Amazon SNS, Amazon CloudWatch, AWS CloudTrail

## Configuración Requerida (Setup)
Para desplegar este proyecto en tu propia cuenta de AWS, necesitarás configurar:
1. **Amazon Cognito:** Un User Pool configurado para inicio de sesión con correo electrónico.
2. **Amazon DynamoDB:** 
   - Tabla `LostFoundItems` (Partition Key: `itemID`).
   - Tabla `LostFoundMatches` (Partition Key: `matchID`).
3. **Amazon S3:** Un bucket privado para alojar las imágenes (evidencias gráficas).
4. **Amazon Bedrock:** Acceso habilitado al modelo `amazon.nova-lite-v1:0` en tu región.
5. **Amazon API Gateway & Lambda:** Configurar integración Proxy y habilitar CORS para los endpoints `/items`, `/matches`, `/chat` y `/upload-url`.

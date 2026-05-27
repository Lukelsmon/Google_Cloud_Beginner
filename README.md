<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=FFFFFF&height=120&section=header"/>

# Google_Cloud_Beginner
Starting learning about Google Cloud in general

<div align=center>
  <h1> Dados </h1>
</div>

<h2>Imagine uma empresa que precisa otimizar sua cadeia de suprimentos analisando dados históricos e prevendo padrões futuros de demanda. Eles têm dados em vários formatos de múltiplos sistemas e precisam torná-los acessíveis para analistas de negócios. Qual abordagem do Google Cloud melhor suportaria seus objetivos de transformação de dados?</h2>

<h3>
  Opções corretas: Arquitetura de data lake com Cloud Storage, Dataproc e BigQuery
</h3>

<p>
  E porquê essas são as opções corretas?
  Arquitetura de data lake com Cloud Storage servindo para dados brutos, Dataproc para processamento e BigQuery para análise
</p>

<p>
  Esta abordagem fornece uma solução mais flexível e escalável para diversas necessidades de dados da empresa. O Cloud Storage serve como a base do data lake, armazenando dados brutos em seu formato nativo sem exigir transformação na ingestão, assim preservando as informações originais e acomoda vários tipos de dados de múltiplos sistemas.
</p>
<p>
  O DataProc fornece clusters gerenciados de Hadoop e Spark (são ambientes computacionais em nuvem pré-configurados que processam grandes volumes de dados [Big Data]), podendo transformar esses dados brutos em escala, assim lidando com operações complexas de ETL (Extract, Transform, Load. É um processo de integração de dados usado para coletar informações de várias fontes, padronizá-las e organizá-las em um único repositório central, como um banco de dados ou data warehouse, para análise e tomada de decisões).
</p>
<p>
  Já o BigQuery completa a arquitetura como um data warehouse (É um sistema centralizado voltado para Business Intelligence (BI) e tomada de decisões) sem servidor onde os dados processados podem ser analisados usando SQL, assim permitindo que analistas de negócios executem consultas complexas sem gerenciar infraestrutura. E por fim, data lake é um repositório massivo projetado para armazenar grandes volumes de dados em seu estado original, ou seja, mais flexível que o data warehouse.
</p>

<h3> E sobre outras opções que estavam "incorretas"? </h3>

<p>
  Existia opções como Cloud Spanner e Computer Engine, porém, mesmo como opções talvez boas, não é exatamente o que a empresa busca. O Cloud Spanner é um banco de dados globalmente distribuído e muito consistente, que foi projetado para cargas de trabalho transacionais tal qual exigem alta disponibilidade e consistência global, no entanto, não é otimizado para processamento analítico de dados históricos e demasiado caro.
</p>

<p>
  E sobre o Computer Engine com a função de executar scripts de análise personalizados exigiria que a empresa construísse e mantivesse uma própria infraestrutura analítica, tal qual adicionaria uma sobrecarga operacional.
</p>

<p>
  Além de outras opções como Cloud SQL e App Engine, que já é um caso de maior prejuízo para a empresa. O Cloud SQL é um serviço de banco de dados relacional que teria dificuldades com escala e variedade de dados de uma operação logística global. Somente projetado para cargas de trabalho transacionais. E a respeito do App Engine, construir um painel de análise personalizado exige um grande esforço de desenvolvimento e não forneceria flexibilidade analítica que os analistas de négocios precisam para explorar dados e descobrir novos padrões.
</p>



<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=FFFFFF&height=120&section=footer"/>

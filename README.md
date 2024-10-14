# RELAT-RIO-DE-IMPLEMENTA-O-DE-SERVI-OS-AWS

# RELATÓRIO DE IMPLEMENTAÇÃO DE SERVIÇOS AWS

**Data**: 13/09/2024.  
**Empresa**: Abstergo Industries.
**Responsável**: João Matheus Magalhães.

---

## Introdução  
Este relatório apresenta o processo de implementação de serviços em nuvem na Abstergo Industries, um hub de distribuição farmacêutica que atua como revendedora para farmácias e empresas. O projeto foi realizado com o objetivo de reduzir custos operacionais e melhorar a eficiência tecnológica por meio da utilização de serviços da Amazon Web Services (AWS). Foram implementados três serviços principais que, juntos, garantem alta disponibilidade, escalabilidade e segurança dos dados, além de otimizar o desempenho das operações da empresa.

---

## Descrição do Projeto  

O projeto de implementação foi dividido em três etapas principais, cada uma abordando aspectos críticos da infraestrutura de TI da Abstergo Industries.

### Etapa 1: Amazon S3 - Armazenamento de Dados  

**Descrição Técnica**:  
O Amazon S3 foi utilizado como o principal serviço de armazenamento de dados da Abstergo, proporcionando alta durabilidade, escalabilidade e segurança. Com isso, foi possível armazenar grandes volumes de dados, como históricos de transações, inventários e informações sensíveis, garantindo que os dados estejam sempre acessíveis e protegidos.

**Benefícios**:  
- **Redução de Custos**: O S3 opera com um modelo de pagamento por uso, permitindo que a empresa pague apenas pelo espaço utilizado.
- **Alta Disponibilidade e Durabilidade**: Garantia de durabilidade de 99.999999999% (11 noves) para todos os objetos armazenados.
- **Segurança**: Implementação de criptografia tanto em repouso quanto em trânsito, e controle de acesso por meio do IAM.
- **Backup e Disaster Recovery**: Replicação dos dados em múltiplas regiões para garantir disponibilidade mesmo em situações de falhas.

**Considerações**:  
- **Latência**: A latência pode ser uma preocupação para operações que exigem alta velocidade de leitura. O uso do Amazon CloudFront pode ser considerado para otimizar a entrega de conteúdo.
- **Custo de Saída de Dados**: A saída de grandes volumes de dados do S3 pode gerar custos adicionais, sendo importante monitorar e gerenciar essa utilização.

### Etapa 2: Amazon EC2 - Servidores Virtuais  

**Descrição Técnica**:  
Foi implementado o Amazon EC2 para substituir os servidores físicos da Abstergo. Este serviço de servidores virtuais oferece escalabilidade e controle total sobre o ambiente de computação, possibilitando ajustar a capacidade de acordo com a demanda e otimizando o uso de recursos.

**Benefícios**:  
- **Elasticidade**: Permite escalar recursos de forma automática conforme a demanda aumenta ou diminui.
- **Redução de Custos de Infraestrutura**: Elimina a necessidade de hardware físico e manutenção, além de reduzir o consumo de energia.
- **Segurança de Rede**: Grupos de segurança e VPCs garantem a comunicação segura entre os sistemas.
- **Alto Controle e Customização**: Permite configurar instâncias conforme as necessidades específicas da operação.

**Considerações**:  
- **Gerenciamento Contínuo**: A empresa deve monitorar o uso das instâncias para evitar custos desnecessários por subutilização.
- **Instâncias Sob Demanda vs. Reservadas**: A escolha correta entre instâncias reservadas e sob demanda deve ser feita conforme a previsibilidade da carga de trabalho.

### Etapa 3: Amazon RDS - Gerenciamento de Banco de Dados  

**Descrição Técnica**:  
O Amazon RDS foi utilizado para gerenciar os bancos de dados relacionais da empresa, proporcionando backup automatizado, escalabilidade e alta disponibilidade por meio da configuração Multi-AZ. A solução escolhida foi o PostgreSQL, que oferece flexibilidade e robustez necessárias para o gerenciamento de dados críticos.

**Benefícios**:  
- **Automação de Tarefas Administrativas**: Backup, atualização de software e monitoramento são feitos automaticamente, liberando a equipe de TI para focar em outras tarefas.
- **Alta Disponibilidade**: A configuração Multi-AZ garante que o banco de dados continue disponível mesmo em casos de falhas.
- **Escalabilidade**: Permite aumentar a capacidade de armazenamento e processamento conforme necessário.
- **Segurança**: Criptografia de dados em repouso e em trânsito, além de isolamento de rede por meio de VPCs.

**Considerações**:  
- **Custo com Multi-AZ**: A configuração Multi-AZ garante alta disponibilidade, mas gera custos adicionais.
- **Limitações de Controle**: Embora o RDS automatize muitas tarefas, pode ser limitado para equipes que precisem de maior controle sobre a administração de bancos de dados.

---

## Conclusão  

A implementação dos serviços AWS na Abstergo Industries atendeu às expectativas e trouxe benefícios significativos para a empresa. A redução de custos operacionais, a melhoria na disponibilidade dos sistemas e a segurança dos dados foram os principais ganhos obtidos. A elasticidade e escalabilidade proporcionadas pelos serviços como EC2 e S3 asseguram que a Abstergo possa crescer e atender às variações de demanda sem precisar investir em infraestrutura física adicional.

Além disso, a automação dos processos administrativos no Amazon RDS e a alta disponibilidade garantem que as operações da empresa estejam sempre ativas, minimizando interrupções e maximizando a produtividade. Recomenda-se a continuidade da utilização desses serviços e a exploração de novas tecnologias AWS, como AWS Lambda, para otimizar ainda mais os processos e reduzir custos futuros.

---

## Anexos  

- Documentação do Amazon S3(https://aws.amazon.com/free/?gclid=CjwKCAjw3624BhBAEiwAkxgTOio0EuheaQdjlsPk0y5-S8B5EAAYtGPCf1PTQtqsOj2Lf0tl1jrSYBoCRp0QAvD_BwE&all-free-tier.sort-by=item.additionalFields.SortRank&all-free-tier.sort-order=asc&awsf.Free%20Tier%20Categories=categories%23storage&trk=3daf7be6-997a-4e7c-af79-be4074c210e4&sc_channel=ps&ef_id=CjwKCAjw3624BhBAEiwAkxgTOio0EuheaQdjlsPk0y5-S8B5EAAYtGPCf1PTQtqsOj2Lf0tl1jrSYBoCRp0QAvD_BwE:G:s&s_kwcid=AL!4422!3!536394070228!p!!g!!aws%20s3!12024810840!115492236705&awsf.Free%20Tier%20Types=*all)
- Guia de utilização do Amazon EC2(https://aws.amazon.com/pt/ec2/?gclid=CjwKCAjw3624BhBAEiwAkxgTOriAlEi1mx3Xen8bU4eUKjlHOMcHCrmDkWpEE-IPWWIfLg4r0tWEgBoCyMMQAvD_BwE&trk=273714db-4e14-42ba-be75-e3e36c4bc786&sc_channel=ps&ef_id=CjwKCAjw3624BhBAEiwAkxgTOriAlEi1mx3Xen8bU4eUKjlHOMcHCrmDkWpEE-IPWWIfLg4r0tWEgBoCyMMQAvD_BwE:G:s&s_kwcid=AL!4422!3!589890540409!p!!g!!amazon%20aws%20ec2!16393914376!135045746338)
- Manual de administração do Amazon RDS(https://aws.amazon.com/free/database/?gclid=CjwKCAjw3624BhBAEiwAkxgTOgelxcwhaAZb8Y9wiNNyoMKdXLNL0caXp5aFl3i6BY86gF1DnPMaAhoCMN4QAvD_BwE&trk=eca03f9c-ce0f-4704-b08e-e6fe66f1f54d&sc_channel=ps&ef_id=CjwKCAjw3624BhBAEiwAkxgTOgelxcwhaAZb8Y9wiNNyoMKdXLNL0caXp5aFl3i6BY86gF1DnPMaAhoCMN4QAvD_BwE:G:s&s_kwcid=AL!4422!3!548640877340!p!!g!!aws%20rds!12024809973!118832470929)

---

**Assinatura do Responsável pelo Projeto**:  
João Matheus Magalhães

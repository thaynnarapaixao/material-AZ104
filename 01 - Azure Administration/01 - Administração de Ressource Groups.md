# O que são recursos ?

Recurso é tudo aquilo que existe em um determnado local dentro do seu cloud azure . Esses recursos variam entre vms, bancos de dados, redes, storage e etc. São como os recursos de rede mas alocados sobre uma parte do seu tenant no azure
Esses Recursos são aglomerados dentro do azure em uma localidade chamada ressource group.

----

## O que é um resource Group ?

![Resource Group](img/image-32.png)
</br>
----

Um grupo de recursos é um contêiner que mantém os recursos relacionados a uma solução do Azure. O grupo de recursos pode incluir todos os recursos para a solução ou apenas os recursos que você deseja gerenciar como um grupo de usuários. 
Você decide como deseja alocar recursos para grupos de recursos com base no que faz mais sentido para sua organização. 
Em geral, adicione recursos que compartilham o mesmo ciclo de vida no mesmo grupo de recursos, para que você possa implantar, atualizar e excluí-los como um grupo facilmente.

O grupo de recursos armazena metadados sobre os recursos. 
Portanto, quando você especifica um local para o grupo de recursos, especifica onde os metadados são armazenados. Por motivos de conformidade, talvez você precise garantir que os dados sejam armazenados em determinada região.

*Criando um resource group*

O resource Group pode ser criado via interface gráfica ( Azure portal), via cli ou Powershell interagindo com os gateways de api do azure.
O Ressource Group é gerenciado pelo [resource group manager](https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/overview) que ao receber as calls do usuário para gerenciar os recursos do azure repassa essa funcção para o [ARM](https://www.google.com/search?client=firefox-b-d&q=azure+arm) para criação dos recursos e se responsailiza somente pelo isolamento de cada um deles dentro do resource group criado.

Para que possamos interagir com os ressource Groups e com o ARM é necessário que tenhamso uma relação de confiança estabelecida com o Azure ad via autenticação. Essa relação garante que possamos adiministrar cada um desses recursos via identidade garantindo compliance e segurança sobre os recursos criados. Sendo assim sempre teremos o seguinte cenário :

```Efetuar login > Selecionar Grupo de recurso ou Cria-lo > Criar Recurso ```

----

## Keypoints :
 - Resources são gerenciados pela azure! Maquinas virtuais, rede, storage e etc
   - Resource Groups ( RG ) São containers que aglomeram os recursos
     - Esses Grupos de recursos ficam abaixo de uma Subscription que é ligada aos custos.

- Recursos podem ser gerenciados via ARM [resource group manager](https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/overview)
- Cada Recuso tem seu Provider, que é ligado ao tipo de recurso que é cedido.

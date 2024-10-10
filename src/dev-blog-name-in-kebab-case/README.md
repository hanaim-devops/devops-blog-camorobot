# Terraform: Infrastructure as Code eenvoudig gemaakt

**Auteur:** Kevin Noppers, oktober 2024.

In het kader van de HAN-minor DevOps onderzoek ik de automatiseringstool Terraform. Deze tool is geen onderdeel van de lessen, maar past perfect binnen de onderwerpen Infrastructure as Code (IaC) en Continuous Delivery. Het doel van dit onderzoek is om te begrijpen hoe Terraform werkt en hoe deze technologie kan worden ingezet binnen een klein- en grootschalig DevOps-project. In deze blogpost zal ik uitleggen wat Terraform is, welke problemen het oplost, gevolgd door een hands-on demo waarin we een eenvoudige AWS-omgeving opzetten. Tot slot vergelijken we Terraform met andere tools en bespreken we waarom je voor Terraform zou kunnen kiezen.

![Terraform Logo](https://icon.icepanel.io/Technology/svg/HashiCorp-Terraform.svg)

## Wat is Terraform?
Terraform is een open-source infrastructuurbeheer tool ontwikkeld door HashiCorp. Het maakt het mogelijk om infrastructuur te definiëren en te beheren via declaratieve configuratiebestanden (HashiCorp, z.d.). Dit betekent dat je kunt beschrijven welke infrastructuur je nodig hebt, en Terraform zorgt ervoor dat deze infrastructuur gecreëerd en beheerd wordt. Terraform ondersteunt verschillende cloudproviders zoals AWS, Google Cloud, Azure.

Een groot voordeel van Terraform is dat het werkt volgens het principe van Infrastructure as Code (IaC). Dit houdt in dat je infrastructuur kunt beheren met code, wat zorgt voor consistentie, versiebeheer en automatisering in de opbouw en onderhoud van je infrastructuur.


## Wat zijn de kernprincipes van Terraform en Infrastructure as Code (IaC)?
Terraform is gebaseerd op het concept van Infrastructure as Code (IaC), waarbij infrastructuur via code wordt beheerd en geconfigureerd in plaats van handmatige handelingen. Dit brengt een belangrijke verschuiving teweeg in hoe IT-teams infrastructuur beheren. In plaats van een stap-voor-stap instructie (procedureel) te geven over hoe componenten worden opgezet, beschrijven ontwikkelaars in Terraform wat de gewenste eindstaat van de infrastructuur moet zijn (declaratief). Deze benadering vermindert de complexiteit van infrastructuurbeheer, omdat Terraform automatisch de noodzakelijke stappen uitvoert om de gewenste toestand te bereiken. Dit gebeurt met behulp van een speciaal ontworpen taal, de HashiCorp Configuration Language (HCL), die eenvoudig te lezen en te schrijven is.

Het gebruik van IaC en tools zoals Terraform maakt het mogelijk om infrastructuurconfiguraties vast te leggen in versiebeheersystemen zoals Git. Dit biedt meerdere voordelen, waaronder traceerbaarheid en controle over elke wijziging in de infrastructuur. Teams kunnen eenvoudig terugkeren naar vorige versies als er een probleem optreedt, wat de betrouwbaarheid van het systeem vergroot. Daarnaast biedt automatisering door IaC een significante vermindering van menselijke fouten. Aangezien alle configuraties via code worden beheerd, wordt de kans op verkeerde configuraties of mislukte implementaties geminimaliseerd. Hierdoor worden systemen veiliger en stabieler.

## Wat zijn de voordelen van Terraform ten opzichte van andere infrastructuurbeheer tools?
Terraform onderscheidt zich van andere infrastructuurbeheer tools zoals AWS CloudFormation en Ansible door zijn unieke combinatie van multi-cloudondersteuning en geavanceerd state-management. Waar AWS CloudFormation specifiek is ontworpen voor het beheren van infrastructuur binnen de AWS-omgeving, biedt Terraform de flexibiliteit om infrastructuur te beheren over meerdere cloudplatformen. Dit betekent dat organisaties die zowel met AWS, Azure als Google Cloud werken, met Terraform hun volledige infrastructuur met één tool kunnen beheren. Deze multi-cloudondersteuning zorgt ervoor dat bedrijven niet beperkt zijn tot één cloudprovider, wat hen de vrijheid geeft om hun infrastructuur flexibel in te richten en eenvoudig van cloudprovider te wisselen.

Een ander onderscheidend kenmerk van Terraform is zijn state-management. Dit houdt in dat Terraform bijhoudt wat de huidige status van de infrastructuur is. Wanneer er wijzigingen worden aangebracht, vergelijkt Terraform de gewenste infrastructuur met de huidige staat en voert alleen de noodzakelijke wijzigingen door. Dit voorkomt onbedoelde veranderingen en zorgt voor een consistent beheer van de infrastructuur. Dit state-management vermindert ook de kans op foutieve of ongewenste aanpassingen, waardoor de betrouwbaarheid van het systeem toeneemt.

Terraform’s declaratieve aanpak biedt nog een extra voordeel. In plaats van precies te definiëren hoe iets moet worden uitgevoerd, beschrijft de gebruiker eenvoudig wat de gewenste eindstaat is (zoals het opstarten van een EC2-instance). Terraform zorgt vervolgens voor het uitvoeren van alle noodzakelijke stappen om dit doel te bereiken. Deze declaratieve aanpak verlaagt de complexiteit in vergelijking met tools die werken met procedurele scripts, omdat de gebruiker zich niet hoeft te richten op de exacte uitvoering van de stappen, maar alleen op het eindresultaat. Dit maakt Terraform gemakkelijker te gebruiken en minder foutgevoelig voor complexe infrastructuren.

## Hoe ondersteunt Terraform de schaalbaarheid en onderhoudbaarheid van grote infrastructuren?
Terraform ondersteunt de schaalbaarheid en onderhoudbaarheid van grote infrastructuren door zijn modulariteit en state-management, wat het eenvoudig maakt om infrastructuren op grote schaal consistent en efficiënt te beheren. Met modules kunnen herbruikbare configuraties worden gemaakt die je voor verschillende omgevingen kunt inzetten. Dit maakt het onderhoud eenvoudiger, omdat je eenmaal geschreven code kunt hergebruiken zonder deze telkens opnieuw te moeten schrijven. In grote infrastructuren, waarin verschillende onderdelen herhaaldelijk worden gebruikt (zoals netwerken of databases), is dit essentieel voor efficiënt beheer en schaalbaarheid.

Daarnaast biedt Terraform workspaces, die het beheer van meerdere omgevingen zoals development, staging en productie binnen één configuratie mogelijk maken. Elke omgeving kan afzonderlijk worden beheerd, maar alle omgevingen delen dezelfde infrastructuurbasis. Dit maakt het eenvoudiger om wijzigingen in de ene omgeving veilig te testen voordat ze worden uitgerold naar productie, zonder de configuratie opnieuw te moeten opzetten.

## Conslusie
In conclusie draagt Terraform in hoge mate bij aan het efficiënt beheren van cloudinfrastructuur door middel van Infrastructure as Code (IaC). Als open-source tool biedt Terraform gebruikers de mogelijkheid om cloudinfrastructuur declaratief te definiëren, waardoor handmatige configuraties en bijbehorende fouten worden geminimaliseerd. Deze declaratieve benadering, gecombineerd met de HashiCorp Configuration Language (HCL), stelt teams in staat om infrastructuurconfiguraties eenvoudig vast te leggen, te beheren en bij te houden in versiebeheersystemen. Dit verhoogt de betrouwbaarheid en veiligheid van de infrastructuur door consistentie en herhaalbaarheid te waarborgen.

Een van de grootste voordelen van Terraform ten opzichte van andere tools zoals AWS CloudFormation en Ansible is zijn multi-cloudondersteuning, wat organisaties de flexibiliteit geeft om infrastructuren over meerdere cloudproviders te beheren met één enkele tool. Het geavanceerde state-management van Terraform zorgt ervoor dat wijzigingen gecontroleerd en consistent worden doorgevoerd, waardoor de kans op fouten aanzienlijk afneemt.

Daarnaast maakt Terraform’s modulariteit het onderhoud van grote infrastructuren eenvoudig. Herbruikbare configuraties in de vorm van modules zorgen voor efficiëntie, terwijl workspaces het beheer van meerdere omgevingen binnen één configuratie mogelijk maken. Deze eigenschappen maken Terraform niet alleen geschikt voor kleinere infrastructuren, maar ook bijzonder krachtig voor organisaties die snel willen schalen of complexe infrastructuren moeten beheren.

Kortom, Terraform biedt een flexibele, schaalbare en betrouwbare manier om cloudinfrastructuur efficiënt te beheren als code, en is daarmee een essentieel hulpmiddel voor moderne DevOps-praktijken.


## Hands-on: Een AWS-omgeving opzetten met Terraform
In deze demo laten we zien hoe je met Terraform een eenvoudige AWS-infrastructuur opzet, waaronder een VPC (Virtual Private Cloud) en een EC2-instance.
![AWS Logo](https://icon.icepanel.io/Technology/png-shadow-512/AWS.png)

### Installatie van Terraform

Om aan de slag te gaan met Terraform, installeren we de tool eerst op onze lokale machine. Dit kan eenvoudig door de volgende stappen te volgen (MacOS):

1. Download de Terraform binary:
    ```bash
    brew install terraform
    ```
2. Controleer of Terraform correct geïnstalleerd is:
    ```bash
    terraform -v
    ```
3. Download de AWS CLI (Command Line Interface) om te communiceren met AWS:
    ```bash
    brew install awscli
    ```
4. Controleren of de AWS CLI correct is geïnstalleerd:
    ```bash
    aws --version
    ```
5. Configureer de AWS CLI met je AWS-access key en secret key:
    ```bash
    aws configure
    ```

### Terraform-configuratiebestanden

Maak een nieuw Terraform-project aan met de volgende commando:
```bash
mkdir terraform-aws-demo && cd terraform-aws-demo
```
Maak vervolgens een nieuw bestand `main.tf` aan en voeg de volgende Terraform-configuratie toe:
```hcl
provider "aws" {
  region = "eu-west-1"
}

resource "aws_instance" "Terraform-AWS-Demo" {
  count         = 3
  ami           = "ami-099a8245f5daa82bf"
  instance_type = "t2.micro"

  tags = {
    Name = "TerraformExampleInstance-${count.index + 1}"
  }
}

```

### Terraform initialiseren en uitvoeren

Voer de volgende commando's uit om Terraform te initialiseren en de infrastructuur op te zetten. Doormiddel van `terraform init` wordt de provider geïnitialiseerd en worden de benodigde plugins gedownload. Met `terraform plan` wordt een overzicht gegeven van de wijzigingen die Terraform zal aanbrengen. Met `terraform apply` worden de wijzigingen daadwerkelijk doorgevoerd.
```bash
terraform init
```
```bash
terraform plan
```
```bash
terraform apply
```

### AWS-infrastructuur

Na het uitvoeren van de Terraform-configuratie, kun je de aangemaakte AWS-infrastructuur bekijken in de AWS Management Console. Hier zie je de aangemaakte EC2-instances en de VPC.
![AWS Console](./Images/AWS-Console.png)

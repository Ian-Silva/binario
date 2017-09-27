# binario

#include <stdio.h>

int main(int argc, char **argv)
{
    int n=0, m=1;  /*Auxiliadores da transformação binário decimal*/
    int pega, power;  /*Auxiliadores de código*/
    int bin=1, total=0, potenc=1, dek=0;  /*váriaveis da transformação binária decimal*/
    int soma=0, soma1=0;    /*Auxiliadores do contador de digitos*/
    int Flag=0,Flagg=0; /*Flag*/
    char operador;  /*OPerador de caractere*/
    int bin1=1, total1=0, potenc1=1, dev=0;   /*Váriaveis da transformação binária decimal*/

    /*Transformação Binario Decimal*/

    scanf("%d",&bin);   /*Leitura do número binário*/
    if(bin==0)/*Caso o valor digitado pelo usuário seja 0 o programa encerra*/
    {
        return 0;
    }

    while(bin!=0)
    {




        Flag=0;
        if(bin==0)/*Caso o valor digitado pelo usuário seja 0 o programa encerra*/
        {
            return 0;
        }

        if(bin<0)
        {
            bin = bin * (-1);
            Flag=1;
        }

        Flagg=0;

        while(bin>0)    /*Faz a transformação de binário para decimal juntamente com o contador de dígitos*/
        {
            if(bin%10!=0 && bin%10!=1)  /*Verificando se há números diferentes de 0 e 1*/
            {
                Flagg=1;    /*Flagg recebe 1*/
            }

            total += bin%10*potenc;
            bin=bin/10;
            potenc = potenc * 2;

            soma++;

        }



        if(soma>8||Flagg==1)  /*Verifica se o valor lido não é maior que 8 digitos*/
        {
            printf("Sua entrada está incorreta!\n");
            scanf("%d",&bin);
        }



    }








    while(bin1!=0)
    {


        scanf(" %c",&operador); /*Leitura do operador*/

        scanf("%d",&bin1);  /*Leitura do segundo binário*/
        printf("\n");


        if(bin1==0)/*Caso o valor digitado pelo usuário seja 0 o programa encerra*/
        {
            return 0;
        }






        while(bin1!=0)
        {


            if(bin1 < 0)
            {
                bin1 = bin1 * (-1);
                Flagg=1;
            }



            Flag = 0;

            while(bin1>0)    /*Faz a transformação de binário para decimal juntamente com o contador de dígitos*/
            {
                if(bin1%10!=0 && bin1%10!=1)  /*Verificando se há números diferentes de 0 e 1*/
                {
                    Flag=1;
                }

                total1 += bin1%10*potenc1;
                bin1=bin1/10;
                potenc1 = potenc1 * 2;

                soma1++;

            }

            if(soma1>8||Flag==1)  /*Verifica se o valor lido não é maior que 8 digitos*/
            {
                printf("Sua entrada está incorreta!\n");
                scanf("%d",&bin1);
            }


        }






        dek = total;
        dev = total1;

        if(operador=='+')   /*Verificando se o operador é de soma*/
        {
            if((Flag == 0 && Flagg == 0) || (Flag == 1 && Flagg == 1))
                power = dek + dev;
            else if(Flag == 1 && Flagg == 0)
            {
                power = (-dek) + dev;
            }
            else if(Flag == 0 && Flagg == 1)
            {
                power = dek + (-dev);
            }

            /*Transformação decimal binária*/

            pega = power; /*pega armazena o valor recebido de power*/

            while(power!=0)
            {
                n = n+power%2*m;
                power = power/2;
                m=m*10;
            }

            printf("Binário: %.8d\n",n);
            printf("Hexadecimal: %x\n",pega);
            printf("Decimal: %d\n",pega);

        }

        if(operador=='-')
        {
            if((Flag == 0 && Flagg == 0) || (Flag == 1 && Flagg == 1))
                power = dek - dev;
            else if(Flag == 1 && Flagg == 0)
            {
                power = (-dek) - dev;
            }
            else if(Flag == 0 && Flagg == 1)
            {
                power = dek - (-dev);
            }

            /*Transformação decimal binária*/

            pega = power; /*pega armazena o valor recebido de power*/

            while(power!=0)
            {
                n = n+power%2*m;
                power = power/2;
                m=m*10;
            }

            printf("Binário: %.8d\n",n);
            printf("Hexadecimal: %x\n",pega);
            printf("Decimal: %d\n",pega);

        }

        if(operador=='*')
        {
            if((Flag == 0 && Flagg == 0) || (Flag == 1 && Flagg == 1))
                power = dek * dev;
            else if(Flag == 1 && Flagg == 0)
            {
                power = (-dek) * dev;
            }
            else if(Flag == 0 && Flagg == 1)
            {
                power = dek * (-dev);
            }

            /*Transformação decimal binária*/

            pega = power; /*pega armazena o valor recebido de power*/

            while(power!=0)
            {
                n = n+power%2*m;
                power = power/2;
                m=m*10;
            }

            printf("Binário: %.8d\n",n);
            printf("Hexadecimal: %x\n",pega);
            printf("Decimal: %d\n",pega);

        }

        if(operador=='/')
        {
            if((Flag == 0 && Flagg == 0) || (Flag == 1 && Flagg == 1))
                power = dek / dev;
            else if(Flag == 1 && Flagg == 0)
            {
                power = (-dek) / dev;
            }
            else if(Flag == 0 && Flagg == 1)
            {
                power = dek / (-dev);
            }

            /*Transformação decimal binária*/

            pega = power; /*pega armazena o valor recebido de power*/

            while(power!=0)
            {
                n = n+power%2*m;
                power = power/2;
                m=m*10;
            }

            printf("Binário: %.8d\n",n);
            printf("Hexadecimal: %x\n",pega);
            printf("Decimal: %d\n",pega);

        }

        total = total1;
        Flag = Flagg;
    }


    return 0;
}

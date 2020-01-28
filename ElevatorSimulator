//--->Author:-Harsh Mankodiya 
//--->Date:-01-01-2020 Date of completion:20-01-2020
//--->Code_Description:-Elevator-Simulation-Code

#include<stdio.h>
#include<stdlib.h>
#define s 100

int sequ[s];
int seqd[s];
int fu=-1,ru=-1,giu=0,gid=0,fd=-1,rd=-1,x,flu=1,fld=1;
void enqu(int n);
void dequ();
int emptycu();
void displayu(int);
void enqd(int n);
void deqd();
int emptycd();
void displayd(int);
void sortu(int);
void resetu();
void sortd(int);
void resetd();

int main(){
	printf("-----------------Elevator Simulator-----------------\n");
	printf("---------------Author:Harsh Mankodiya-------------------\n\n");
	printf("Controls:: press -1 to close the door\nEnter the floor no you want to goto\n\n");
	int i,n,p=0,u=1,d=0,cp=0,tempu=0,zefd=0,zefu=0,tempd=0,templ,fll=0;
	char val;
	int tic,diff,j,t,f=0,d1,d2;
	printf("Enter The no of floors in the building: ");
	scanf("%d",&n);	
	do{
		
			while(1){
			scanf("%d",&p);
			if(p==-1){
				break;
			}
			else{
			
			if(p>cp){
				enqu(p);
				tempu++;
				u=1;
			}
			
			else{
				enqd(p);
				tempd++;
				gid=tempd-1;
				d=1;
			}	
			
			}		
		}
		
	if(u==1&&d==0){
//		f1:
		val='u';
		if(!emptycu()){
		sortu(tempu);
		displayu(tempu);
		cp=sequ[zefu];
		templ=cp;
		zefu++;
		printf("\n<cp%d> ",cp);
		dequ();
		}
		else{
			cp=sequ[zefu];
			flu=0;
			if(emptycd()){
			printf("\nEmpty");
			}
			printf(" <cp %d>",cp);
			zefu=0;
			tempu=0;
			u=0;
		}
	}
	else if(d==1&&u==0){
		val='d';	
		if(!emptycd()){
		sortd(tempd);	
//		printf("  tempd%d ",tempd);
		displayd(tempd);
		cp=seqd[rd];
		printf(" <CP%d>\n",cp);
		deqd();
		templ=seqd[rd];
		}
		else{
			templ=seqd[rd];
			cp=templ;
			if(emptycu()){
				printf("\nEmpty");
			}
			fld=0;
			printf("<cp %d>\n",cp);
			d=0;
			resetd();
			tempd=0;
			gid=0;
		}
	}
	else if(u==1&&d==1){
//		printf("val %c",val);
		if(val=='u'){
			if(!emptycu()){
		sortu(tempu);
		printf("tempu%d",tempu);	
		displayu(tempu);
		for(i=0;i<tempd;i++){
			printf(" %d",seqd[i]);
		}
		cp=sequ[zefu];
		templ=cp;
		zefu++;
		printf("\n<cp%d> ",cp);
		dequ();
		}
		else{
			cp=sequ[zefu];
			flu=0;
			for(i=0;i<tempd;i++){
				printf(" %d",seqd[i]);
			}			
			if(emptycd()){
				printf("\nEmpty");
			}
			printf(" <cp %d>",cp);
			zefu=0;
			tempu=0;
			u=0;
		}
		}
		else if(val=='d'){
			if(!emptycd()){
//				gid=tempd;
				sortd(tempd);	
				displayd(tempd);
				for(i=0;i<tempu;i++){
					printf(" %d",sequ[i]);
				}
				cp=seqd[rd];
				printf(" <CP%d>\n",cp);
				deqd();
				templ=seqd[rd];
			}
			else{
				templ=seqd[rd];
				cp=templ;
				for(i=0;i<tempu;i++){
					printf(" %d",sequ[i]);
				}				
				if(emptycu()){
					printf("\nEmpty");
				}
				for(i=0;i<tempu;i++){
					printf(" %d",sequ[i]);
				}	
				fld=0;
				printf("<cp %d>\n",cp);
				d=0;
				resetd();
				tempd=0;
				gid=0;
			}
		}
		
	}
}while(1);
	
	return 0;
}
void resetu(){
	fu=-1,ru=-1;
}
void resetd(){
	fd=-1,rd=-1;
}
int emptycu(){
	if(fu==ru){
		resetu();
	}
	return ((fu==-1&&ru==-1)||(fu==ru+1));
}
int emptycd(){
	return (rd==fd);
}
void enqu(int n){
	if(fu==-1){
	fu++;
	}
	sequ[++ru]=n;	
}
void enqd(int n){
	if(fd==-1){
	fd++;
	} 
	seqd[++rd]=n;	
}
void sortu(int temp){
//	printf("sortu");
	int i,temp1,swapp=0;
	while(1){
		swapp=0;
		for(i=0;i<temp-1;i++){
			if(sequ[i]>sequ[i+1]){
			temp1=sequ[i];
			sequ[i]=sequ[i+1];
			sequ[i+1]=temp1;
			swapp=1;
			}
		}
		if(swapp==0){
			break;
		}
	}
}
void sortd(int temp){
	int i,temp1,swapp=0;
	while(1){
		swapp=0;
		for(i=0;i<temp-1;i++){
			if(seqd[i]>seqd[i+1]){
			temp1=seqd[i];
			seqd[i]=seqd[i+1];
			seqd[i+1]=temp1;
			swapp=1;
			}
		}
		if(swapp==0){
			break;
		}
	}
}
void displayu(int temp1){
	int i;
	for(i=giu;i<temp1;i++){
		printf("%d ",sequ[i]);
	}
	giu++;
}
void displayd(int temp2){
	int i;
	
	for(i=gid;i>=0;i--){
		printf("%d ",seqd[i]);
	}
	gid--;
}
void deqd(){
	if(!emptycd()){
		rd--;
	}
}
void dequ(){
	if(!emptycu()){
		sequ[fu++]=0;
		if(fu>ru){
			fu=ru+1;
		}
	}
}

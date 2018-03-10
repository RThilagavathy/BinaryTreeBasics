# BinaryTreeBasics
/******************************************************************************

Welcome to GDB Online.
GDB online is an online compiler and debugger tool for C, C++, Python, PHP, HTML, CSS, JS
Code, Compile, Run and Debug online from anywhere in world.

*******************************************************************************/
#include 
struct node
{
    int key;
    struct node *left,*right;
};
struct node *newnode(int item)
{
    struct node *t=(struct node*)malloc(sizeof(struct node));
    t->key=item;
    t->left=t->right=NULL;
    return t;
}
struct node* insert(struct node *t,int data)
{
    if(t==NULL)
       return newnode(data);
    else if(t->keyright=insert(t->right,data);
    else if(t->key>data)
       t->left=insert(t->left,data);
    return t;   
}
void preorder(struct node *t)
{   
    if(t!=NULL)
    {
    printf("%d->",t->key);
    preorder(t->left);
    preorder(t->right);
    }
}
void inorder(struct node *t)
{   
    if(t!=NULL)
    {
    inorder(t->left);
    printf("%d->",t->key);
    inorder(t->right);
    }
}

int findcommonancestor(struct node* t,int data1,int data2)
{
    if(t==NULL)
      return -1;
    if(t->key>data1&&t->key>data2)
      findcommonancestor(t->left,data1,data2);
    else if(t->keykeyright,data1,data2);
    else if(data1<=t->key&&t->key<=data2)
      return t->key;
    return t->key;  
}
int findmin(struct node*t)
{
    if(t==NULL)
      return -1;
    while(t->left!=NULL)
      t=t->left;
    return t->key;  
}
int findmax(struct node*t)
{
    if(t==NULL)
      return -1;
    while(t->right!=NULL)
      t=t->right;
    return t->key;  
}
int main()
{
    struct node *root=NULL;
    root=insert(root,50);
    insert(root,20);
    insert(root,40);
    insert(root,70);
    insert(root,60);
    insert(root,80);
    printf("PREORDER\n");
    preorder(root);
    printf("\n");
    printf("INORDER\n");
    inorder(root);
    printf("\n");
    printf("%d\n",findcommonancestor(root,60,80));
    printf("%d\n",findmin(root));
    printf("%d\n",findmax(root));
    
    return 0;
}




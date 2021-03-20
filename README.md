# Tree-traveral
class Node{
         Node left;
         int data;
         Node right;
         Node(int x){
             data=x;
         }
}

public class tree {
    public static int  inorder(Node root){
        if(root==null)
             return -1;
         inorder(root.left);
         System.out.println(root.data);
         inorder(root.right); 
         return 0;    
}
public static int  preorder(Node root){
    if(root==null)
         return -1;
    System.out.println(root.data);
    preorder(root.left); 
    preorder(root.right); 
     return 0;    
}
public static int  postorder(Node root1){
    if(root1==null)
         return -1;
    postorder(root1.left); 
    postorder(root1.right);
    System.out.println(root1.data); 
    return 0;    
}
  public static void levelorder(Node root1){
      LinkedList<Node> i=new LinkedList<Node>();
      i.offerLast(root1);
      while(!i.isEmpty()){
        Node d=(Node)i.removeFirst();
        System.out.println(d.data);
        if(d.left!=null){

            i.offerLast(d.left);

        }
        if(d.right!=null){
             i.offerLast(d.right);
        }
       
        
    }
    
}
 ##### public static boolean recursearch(Node root,int item) {             //bst search operation
          if(root==null) return false;
          if(root.data==item){
               return true;
          }
          else if(root.data>item){
                  return recursearch(root.left,item);
          }
          else{
                  return recursearch(root.right,item);
          }
    }
  ####   public static boolean itsearch(Node root,int item) {
         while(root!=null){
            if(root.data==item){
                return true;
           }
           else if(root.data>item){
                   root=root.left;
           }
           else{
                   root=root.right;
           }
         }  
        return false;
    }
   ####  public static int ceil(Node root,int item) {          //ceiling in bst
        int res=Integer.MIN_VALUE;
        while(root!=null){
                if(root.data==item){
                    return item;
               }
               else if(root.data>item){
                if(res<root.data){
                        res=root.data;
                }       
                       root=root.left;
               }
               else{
                       
                       root=root.right;
               }
             }   
              return res; 
      }
    public static void main(String[] args) {
        Node root=new Node(20);
        Node i=new Node(21);
        Node j=new Node(22);
        Node k=new Node(23);
        Node l=new Node(24);
        Node m=new Node(25);
        Node n=new Node(26);
        root.left=i;
        root.right=j;
        i.left=k;
        i.right=l;
        k.left=m;
        j.right=n;
        System.out.println("################# INORDER #############");
        inorder(root);
        System.out.println("################# PREORDER #############");
        preorder(root);
        System.out.println("################# POSTORDER #############");
        postorder(root);
    
    }
}


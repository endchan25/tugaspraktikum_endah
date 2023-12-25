# tugaspraktikum_endah
Laporan Praktikum

MATERI 1
1. Tree
    A. Terminilogi Tree
   class TreeNode {
    int data;
    TreeNode left, right;

    public TreeNode(int data) {
        this.data = data;
        this.left = this.right = null;
    }
}

public class BinaryTreeExample {
    public static void main(String[] args) {
        // Membuat simpul-simpul (nodes) untuk binary tree
        TreeNode root = new TreeNode(1);
        root.left = new TreeNode(2);
        root.right = new TreeNode(3);
        root.left.left = new TreeNode(4);
        root.left.right = new TreeNode(5);

        // Menampilkan hasil
        System.out.println("Contoh Binary Tree:");
        System.out.println("    1");
        System.out.println("   / \\");
        System.out.println("  2   3");
        System.out.println(" / \\");
        System.out.println("4   5");
    }
}

   B. Binary Search Tree
   1. Binary tree
      class TreeNode {
    int data;
    TreeNode left, right;

    public TreeNode(int data) {
        this.data = data;
    }
}

public class SimpleBinaryTree {
    public static void main(String[] args) {
        // Membuat simpul-simpul (nodes) untuk binary tree
        TreeNode root = new TreeNode(1);
        root.left = new TreeNode(2);
        root.right = new TreeNode(3);
        root.left.left = new TreeNode(4);
        root.left.right = new TreeNode(5);

        // Menampilkan hasil inorder traversal
        System.out.println("Inorder Traversal:");
        inorderTraversal(root);
    }

    // Metode rekursif untuk inorder traversal
    private static void inorderTraversal(TreeNode root) {
        if (root != null) {
            inorderTraversal(root.left);
            System.out.print(root.data + " ");
            inorderTraversal(root.right);
        }
    }
}

2. Binary Search tree
   class TreeNode {
    int key;
    TreeNode left, right;

    public TreeNode(int key) {
        this.key = key;
        this.left = this.right = null;
    }
}

public class SimpleBinarySearchTree {
    private TreeNode root;

    public SimpleBinarySearchTree() {
        root = null;
    }

    public void insert(int key) {
        root = insertRec(root, key);
    }

    private TreeNode insertRec(TreeNode root, int key) {
        if (root == null) {
            return new TreeNode(key);
        }

        if (key < root.key) {
            root.left = insertRec(root.left, key);
        } else if (key > root.key) {
            root.right = insertRec(root.right, key);
        }

        return root;
    }

    public void inorder() {
        inorderTraversal(root);
    }

    private void inorderTraversal(TreeNode root) {
        if (root != null) {
            inorderTraversal(root.left);
            System.out.print(root.key + " ");
            inorderTraversal(root.right);
        }
    }

    public static void main(String[] args) {
        SimpleBinarySearchTree bst = new SimpleBinarySearchTree();

        int[] elements = {50, 30, 20, 40, 70, 60, 80};
        for (int element : elements) {
            bst.insert(element);
        }

        System.out.println("Inorder Traversal:");
        bst.inorder();
    }
}

   C. Traversal
   1. Pre Order
      class TreeNode {
    int key;
    TreeNode left, right;

    public TreeNode(int key) {
        this.key = key;
    }
}

public class SimplePreorderTraversal {
    private TreeNode root;

    public void insert(int key) {
        root = insertRec(root, key);
    }

    private TreeNode insertRec(TreeNode root, int key) {
        if (root == null) return new TreeNode(key);
        if (key < root.key) root.left = insertRec(root.left, key);
        else if (key > root.key) root.right = insertRec(root.right, key);
        return root;
    }

    public void preorder() {
        preorderTraversal(root);
    }

    private void preorderTraversal(TreeNode root) {
        if (root == null) return;
        System.out.print(root.key + " ");
        preorderTraversal(root.left);
        preorderTraversal(root.right);
    }

    public static void main(String[] args) {
        SimplePreorderTraversal tree = new SimplePreorderTraversal();
        int[] elements = {50, 30, 20, 40, 70, 60, 80};
        for (int element : elements) tree.insert(element);

        System.out.println("Preorder Traversal:");
        tree.preorder();
    }
}

2. In Order
   class TreeNode {
    int key;
    TreeNode left, right;

    public TreeNode(int key) {
        this.key = key;
    }
}

public class SimpleInorderTraversal {
    private TreeNode root;

    public void insert(int key) {
        root = insertRec(root, key);
    }

    private TreeNode insertRec(TreeNode root, int key) {
        if (root == null) return new TreeNode(key);
        if (key < root.key) root.left = insertRec(root.left, key);
        else if (key > root.key) root.right = insertRec(root.right, key);
        return root;
    }

    public void inorder() {
        inorderTraversal(root);
    }

    private void inorderTraversal(TreeNode root) {
        if (root == null) return;
        inorderTraversal(root.left);
        System.out.print(root.key + " ");
        inorderTraversal(root.right);
    }

    public static void main(String[] args) {
        SimpleInorderTraversal tree = new SimpleInorderTraversal();
        int[] elements = {50, 30, 20, 40, 70, 60, 80};
        for (int element : elements) tree.insert(element);

        System.out.println("Inorder Traversal:");
        tree.inorder();
    }
}

3. Post Order
   class TreeNode {
    int key;
    TreeNode left, right;

    public TreeNode(int key) {
        this.key = key;
    }
}

public class SimplePostorderTraversal {
    private TreeNode root;

    public void insert(int key) {
        root = insertRec(root, key);
    }

    private TreeNode insertRec(TreeNode root, int key) {
        if (root == null) return new TreeNode(key);
        if (key < root.key) root.left = insertRec(root.left, key);
        else if (key > root.key) root.right = insertRec(root.right, key);
        return root;
    }

    public void postorder() {
        postorderTraversal(root);
    }

    private void postorderTraversal(TreeNode root) {
        if (root == null) return;
        postorderTraversal(root.left);
        postorderTraversal(root.right);
        System.out.print(root.key + " ");
    }

    public static void main(String[] args) {
        SimplePostorderTraversal tree = new SimplePostorderTraversal();
        int[] elements = {50, 30, 20, 40, 70, 60, 80};
        for (int element : elements) tree.insert(element);

        System.out.println("Postorder Traversal:");
        tree.postorder();
    }
}

4. Level Order
   import java.util.LinkedList;
import java.util.Queue;

class TreeNode {
    int key;
    TreeNode left, right;

    public TreeNode(int key) {
        this.key = key;
    }
}

public class SimpleLevelOrderTraversal {
    private TreeNode root;

    public void insert(int key) {
        root = insertRec(root, key);
    }

    private TreeNode insertRec(TreeNode root, int key) {
        if (root == null) return new TreeNode(key);
        if (key < root.key) root.left = insertRec(root.left, key);
        else if (key > root.key) root.right = insertRec(root.right, key);
        return root;
    }

    public void levelOrder() {
        if (root == null) return;

        Queue<TreeNode> queue = new LinkedList<>();
        queue.add(root);

        while (!queue.isEmpty()) {
            TreeNode current = queue.poll();
            System.out.print(current.key + " ");

            if (current.left != null) queue.add(current.left);
            if (current.right != null) queue.add(current.right);
        }
    }

    public static void main(String[] args) {
        SimpleLevelOrderTraversal tree = new SimpleLevelOrderTraversal();
        int[] elements = {50, 30, 20, 40, 70, 60, 80};
        for (int element : elements) tree.insert(element);

        System.out.println("Level Order Traversal:");
        tree.levelOrder();
    }
}


MATERI 2
1. Searching
   A. Squensial Search
   public class SimpleSequentialSearch {
    public static boolean searchActivity(String[] activities, String target) {
        for (String activity : activities) {
            if (activity.equals(target)) {
                return true; // Mengembalikan true jika kegiatan ditemukan
            }
        }
        return false; // Mengembalikan false jika kegiatan tidak ditemukan
    }

    public static void main(String[] args) {
        String[] activityList = {"Membaca", "Berlari", "Belajar", "Bermain", "Tidur"};
        String targetActivity = "Belajar";

        if (searchActivity(activityList, targetActivity)) {
            System.out.println("Kegiatan " + targetActivity + " ditemukan dalam daftar.");
        } else {
            System.out.println("Kegiatan " + targetActivity + " tidak ditemukan dalam daftar.");
        }
    }
}

B. Interpolation Search
   public class SimpleActivityInterpolationSearch {
    public static int interpolationSearch(String[] activities, String target) {
        int low = 0;
        int high = activities.length - 1;

        while (low <= high && target.compareTo(activities[low]) >= 0 && target.compareTo(activities[high]) <= 0) {
            if (low == high) {
                if (activities[low].equals(target)) {
                    return low; // Mengembalikan indeks jika kegiatan ditemukan
                }
                return -1; // Mengembalikan -1 jika kegiatan tidak ditemukan
            }

            int pos = low + ((target.compareTo(activities[low]) * (high - low)) / (activities[high].compareTo(activities[low])));

            if (activities[pos].equals(target)) {
                return pos; // Mengembalikan indeks jika kegiatan ditemukan
            }

            if (activities[pos].compareTo(target) < 0) {
                low = pos + 1;
            } else {
                high = pos - 1;
            }
        }

        return -1; // Mengembalikan -1 jika kegiatan tidak ditemukan
    }

    public static void main(String[] args) {
        String[] activityList = {"Belajar", "Bermain", "Makan", "Tidur", "Olahraga", "Bekerja"};
        String targetActivity = "Olahraga";

        int result = interpolationSearch(activityList, targetActivity);

        if (result != -1) {
            System.out.println("Kegiatan " + targetActivity + " ditemukan pada indeks: " + result);
        } else {
            System.out.println("Kegiatan " + targetActivity + " tidak ditemukan dalam daftar.");
        }
    }
}

C. Binary Search
public class SimpleActivityBinarySearch {
    public static int binarySearch(String[] activities, String target) {
        int low = 0;
        int high = activities.length - 1;

        while (low <= high) {
            int mid = low + (high - low) / 2;

            int compareResult = target.compareTo(activities[mid]);

            if (compareResult == 0) {
                return mid; // Mengembalikan indeks jika kegiatan ditemukan
            } else if (compareResult < 0) {
                high = mid - 1;
            } else {
                low = mid + 1;
            }
        }

        return -1; // Mengembalikan -1 jika kegiatan tidak ditemukan
    }

    public static void main(String[] args) {
        String[] activityList = {"Belajar", "Bermain", "Makan", "Tidur", "Olahraga", "Bekerja"};
        String targetActivity = "Olahraga";

        int result = binarySearch(activityList, targetActivity);

        if (result != -1) {
            System.out.println("Kegiatan " + targetActivity + " ditemukan pada indeks: " + result);
        } else {
            System.out.println("Kegiatan " + targetActivity + " tidak ditemukan dalam daftar.");
        }
    }
}


MATERI 3
1. Hash Table
   A. Hash Function
   public class SimpleHashFunctionExample {
    public static void main(String[] args) {
        String input = "Hello, Simple Hash Function!";

        // Menggunakan metode hashCode() untuk menghasilkan nilai hash
        int hashValue = input.hashCode();

        System.out.println("Input: " + input);
        System.out.println("Hash Value: " + hashValue);
    }
}

2. Hash Table di Java
   a. direct hash Function
   public class SimpleFruitHashFunction {
    public static int customHash(String fruitName) {
        // Mengambil nilai ASCII karakter pertama dari nama buah
        int hashValue = fruitName.charAt(0);

        return hashValue;
    }

    public static void main(String[] args) {
        String fruitName = "Apple";

        // Menggunakan customHash untuk menghasilkan nilai hash
        int hashValue = customHash(fruitName);

        System.out.println("Fruit: " + fruitName);
        System.out.println("Hash Value: " + hashValue);
    }
}

2. Step Hash Function
   public class StepFruitHashFunction {
    public static int customHash(String fruitName) {
        int hashValue = 0;

        // Menjumlahkan nilai ASCII dari setiap huruf dalam nama buah
        for (int i = 0; i < fruitName.length(); i++) {
            hashValue += fruitName.charAt(i);
        }

        // Mengambil sisa hasil bagi untuk mendapatkan nilai hash
        hashValue = hashValue % 100; // Contoh: Menggunakan 100 sebagai modul

        return hashValue;
    }

    public static void main(String[] args) {
        String fruitName = "Apple";

        // Menggunakan customHash untuk menghasilkan nilai hash
        int hashValue = customHash(fruitName);

        System.out.println("Fruit: " + fruitName);
        System.out.println("Hash Value: " + hashValue);
    }
}

MATERI 4
1. Sorting

   


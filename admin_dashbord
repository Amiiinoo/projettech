<?php
session_start();
require_once 'config.php';

if (!isset($_SESSION['admin_id'])) {
    header('Location: admin_login.php');
    exit;
}

if (!isset($_SESSION['admin_id'])) {
    header('Location: admin_login.php');
    exit;
}

$jeux = $pdo->query("SELECT * FROM jeu ORDER BY id DESC")->fetchAll();
?>

<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Dashboard Admin</title>
    <style>
        body { font-family: Arial, sans-serif; background: #f2f2f2; padding: 20px; }
        h1 { color: #333; }
        a { color: #007BFF; text-decoration: none; }
        table { width: 100%; background: white; border-collapse: collapse; margin-top: 20px; }
        th, td { padding: 10px; border: 1px solid #ccc; text-align: left; }
        th { background: #007BFF; color: white; }
        img { width: 80px; height: auto; }
    </style>
</head>
<body>

<h1>🎮 Tableau de bord Administrateur</h1>
<p><a href="admin_jeu_ajouter.php">➕ Ajouter un nouveau jeu</a> | <a href="admin_logout.php">Se déconnecter</a></p>

<h2>Liste des jeux</h2>

<table>
    <tr>
        <th>Image</th>
        <th>Nom</th>
        <th>Type</th>
        <th>Genre</th>
        <th>Année</th>
        <th>Actions</th>
    </tr>
    <?php foreach ($jeux as $jeu): ?>
        <tr>
            <td>
                <?php if ($jeu['image']): ?>
                    <img src="uploads/<?= htmlspecialchars($jeu['image']) ?>" alt="<?= htmlspecialchars($jeu['nom']) ?>">
                <?php endif; ?>
            </td>
            <td><?= htmlspecialchars($jeu['nom']) ?></td>
            <td><?= htmlspecialchars($jeu['type']) ?></td>
            <td><?= htmlspecialchars($jeu['genre']) ?></td>
            <td><?= htmlspecialchars($jeu['annee_sortie']) ?></td>
            <td>
                <a href="admin_jeu_modifier.php?id=<?= $jeu['id'] ?>">✏️ Modifier</a> |
                <a href="admin_jeu_supprimer.php?id=<?= $jeu['id'] ?>" onclick="return confirm('Confirmer la suppression ?')">🗑️ Supprimer</a>
            </td>
        </tr>
    <?php endforeach; ?>
</table>

</body>
</html>

## 1. Buscar os nomes de todos os alunos que frequentam alguma turma do professor 'JOAO PEDRO'.

```bash
SELECT aluno.nome
FROM turma JOIN professor ON turma.professor_id = professor.id
      JOIN aluno_turma ON aluno_turma.turma_id = turma.id
      JOIN aluno ON aluno.id = aluno_turma.aluno_id
WHERE professor.nome = "JOAO PEDRO";
```

## 2. Buscar os dias da semana que tenham aulas da disciplina 'MATEMATICA'.

```bash
SELECT turma.dia_da_semana
FROM turma JOIN disciplina ON turma.disciplina_id = disciplina.id
WHERE disciplina.nome = "MATEMATICA";
```

## 3. Buscar todos os alunos que frequentem aulas de 'MATEMATICA' e também 'FISICA'.

```bash
SELECT aluno.nome
FROM aluno JOIN turma ON aluno.id = turma.aluno_id
    JOIN disciplina ON disciplina.id = turma.disciplina_id
WHERE disciplina.nome = "MATEMATICA" AND disciplina.nome = "FISICA";
```

## 4. Buscar as disciplinas que não tenham nenhuma turma.

```bash
SELECT disciplina.nome
FROM turma JOIN disciplina ON turma.disciplina_id = disciplina.id
WHERE NOT turma.disciplina_id;
```

## 5. Buscar os alunos que frequentem aulas de 'MATEMATICA' exceto os que frequentem 'QUIMICA'.

```bash
SELECT aluno.nome
FROM aluno JOIN turma ON aluno.id = turma.aluno_id
    JOIN disciplina ON disciplina.id = turma.disciplina_id
WHERE disciplina.nome = "MATEMATICA" AND NOT disciplina.nome = "QUIMICA";
```
